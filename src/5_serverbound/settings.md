# Settings

### setSettings

Used to set the settings value of an instance. When used by the plugin, the property inspector will receive a `didReceiveSettings` event, and vice versa.

**Sent by:** Plugin, Property inspector

```ts
{
	event: string = "setSettings",
	// A unique value to identify the instance.
	context: string,
	payload: any
}
```

### getSettings

Used to get the settings value of an instance. When used, the OpenAction server will respond with a `didReceiveSettings` event.

**Sent by:** Plugin, Property inspector

```ts
{
	event: string = "getSettings",
	context: string
}
```

### setGlobalSettings

Used to set the plugin-wide global settings value. When used by the plugin, all property inspectors will receive a `didReceiveSettings` event, and vice versa.

**Sent by:** Plugin, Property inspector

```ts
{
	event: string = "setGlobalSettings",
	payload: any
}
```

### getGlobalSettings

Used to get the plugin-wide global settings value. When used, the OpenAction server will respond with a `didReceiveSettings` event.

**Sent by:** Plugin, Property inspector

```ts
{
	event: string = "getGlobalSettings"
}
```
