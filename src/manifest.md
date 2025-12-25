## Manifest

Your plugin needs to contain a `manifest.json` file that supplies key information about your plugin to the OpenAction server. It should be present in the root of your plugin directory. The file is the primary description of your plugin and contains information like the path to your plugin's entrypoint and the actions it provides.

The equivalent Stream Deck SDK documentation on the plugin manifest can be found [here](https://docs.elgato.com/streamdeck/sdk/references/manifest), but it should be noted that the OpenAction API supports multiple extensions to the format documented there that Elgato Stream Deck does not.

#### Icon path format

Multiple properties within a plugin manifest are intended to be references to image files supplied in your plugin. These values should be forward-slash delimited path strings that point to image files, relative to your plugin directory.

However, these paths should be supplied without the file type extension. The OpenAction server will resolve the path by attempting to locate `.svg`,  `@2x.png`, and `.png` versions of your image.

For example, if you set an icon property to `"icon"` in your plugin manifest, the OpenAction server will look for `icon.svg`, `icon@2x.png`, and `icon.png` files in the root of your plugin directory.

#### Example plugin manifest files

- <https://github.com/OpenActionPlugins/counter/blob/main/assets/manifest.json>
- <https://github.com/OpenActionPlugins/system/blob/main/assets/manifest.json>

### Plugin manifest format

`*` is used to denote a required field.

```ts
{
	// * The user-facing name of your plugin
	Name: string,
	// * The user-facing author string (e.g. "nekename")
	Author: string,
	// * The version of your plugin present (e.g. "2.7.2"),
	// as a Semantic Versioning (https://semver.org) compliant version string
	Version: string,
	// * An icon to represent your plugin, in the icon path format described above
	Icon: string,
	// The category your plugin's actions should appear under
	Category: string = "Custom",
	// An icon to represent the category your plugin's actions appear under,
	// which defaults to your plugin's icon if not specified
	CategoryIcon: string | null,
	// The relative path to the property inspector to be displayed for actions that don't specify their own
	PropertyInspectorPath: string | null,
	// Whether the plugin has its own GUI that the user can request to be shown through the OpenAction server
	// (not supported by Elgato Stream Deck)
	HasSettingsInterface: boolean = false,
	// A list of applications which, when launched or terminated, the OpenAction server should notify your plugin
	// (on macOS, set to the application's bundle ID, and on other platforms, set to the executable's name)
	ApplicationsToMonitor: {
		mac: string[],
		windows: string[],
		linux: string[]
	} = {},
	// * The actions provided by your plugin
	Actions: [
		{
			// * The user-facing name of this action
			Name: string,
			// * A unique identifier for this action, in reverse-DNS format,
			// that must start with your plugin's own UUID
			UUID: string,
			// A tooltip that describes the utility of this action
			Tooltip: string = "",
			// * An icon to represent this action, in the icon path format described above
			Icon: string,
			// Whether to automatically toggle the state of this action on key up
			// (only applies to actions with two states)
			DisableAutomaticStates: boolean = false,
			// Whether this action should be visible in the action list
			VisibleInActionsList: boolean = true,
			// Whether this action should be supported in Multi Actions
			SupportedInMultiActions: boolean = true,
			// The relative path to this action's property inspector, if it differs from your plugin's default
			PropertyInspectorPath: string | null,
			// The types of hardware this action should be supported on,
			// such as "Keypad" (buttons) or "Encoder" (dials, sliders or screens)
			Controllers: string[] = ["Keypad"],
			// * The different states this action can be displayed in
			States: [
				{
					// The image of this state in the icon path format described above
					// or set to "actionDefaultImage" to use the action's icon
					Image: string = "actionDefaultImage",
					// The name of this state
					Name: string = "",
					// The text to display over the image when in this state
					Title: string = "",
					// Whether to display the title over the image
					ShowTitle: boolean = true,
					// The colour of the state title
					TitleColor: string = "#FFFFFF",
					// The vertical alignment of the state title, set to "top", "middle", or "bottom"
					TitleAlignment: string = "middle",
					// The font style of the title, set to "Regular", "Bold", "Italic", or "Bold Italic"
					FontStyle: string = "Regular",
					// The font size of the state title in pixels, as rendered on a 72x72px state image
					FontSize: string = "16",
					// Whether to underline the state title or not
					FontUnderline: boolean = false
				}
			]
		}
	],
	// * The operating systems your plugin is supported on
	OS: [
		{
			// * The platform in question, set to "windows", "mac", or "linux"
			Platform: string,
			// The minimum supported version of the platform in question
			Version: string | null
		}
	],
	// The relative path to your plugin executable, to be used if no other code path is specified
	// (HTML5 and Node.js plugins should specify values ending in ".html" or ".js", ".cjs" or ".mjs", respectively)
	CodePath: string | null,
	// Overrides for CodePath by platform, specified using the platform's target triple (https://doc.rust-lang.org/beta/rustc/platform-support.html)
	// (introduced over the CodePathWin, CodePathMac and CodePathLin properties in order to support multiple CPU architectures,
	// but not supported by Elgato Stream Deck or older versions of OpenDeck; therefore, the other properties below should also be specified)
	CodePaths: {
		"x86_64-pc-windows-msvc": string | null,
		"x86_64-apple-darwin": string | null,
		"aarch64-apple-darwin": string | null,
		"x86_64-unknown-linux-gnu": string | null,
		"aarch64-unknown-linux-gnu": string | null
	},
	// An override for CodePath to be used on Windows when not overridden in CodePaths
	CodePathWin: string | null,
	// An override for CodePath to be used on macOS when not overridden in CodePaths
	CodePathMac: string | null,
	// An override for CodePath to be used on Linux when not overridden in CodePaths
	CodePathLin: string | null
}
```
