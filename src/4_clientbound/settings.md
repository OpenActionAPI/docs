# Settings

### didReceiveSettings

Fired in response to the `getSettings` event. Additionally fired to the plugin when the property inspector uses `setSettings`, and vice versa.

**Received by:** Plugin, Property inspector

```ts
{
	event: string = "didReceiveSettings",
	action: string,
	context: string,
	device: string,
	payload: {
		settings: any,
		coordinates: {
			row: number,
			column: number
		},
		isInMultiAction: boolean
	}
}
```

### didReceiveGlobalSettings

Fired in response to the `getGlobalSettings` event. Additionally fired to the plugin when the property inspector uses `setGlobalSettings`, and vice versa.

**Received by:** Plugin, Property inspector

```ts
{
	event: string = "didReceiveGlobalSettings",
	payload: {
		settings: any
	}
}
```
