# Keypad

### keyDown

Fired on keypad key down.

**Received by:** Plugin

```ts
{
	event: string = "keyDown",
	// The action UUID supplied in the plugin manifest.
	// Utilise to determine which action was triggered.
	action: string,
	// A unique value to identify the instance.
	context: string,
	// A unique value to identify the device.
	device: string,
	payload: {
		// Instance settings as set using the `setSettings` event.
		settings: any,
		coordinates: {
			row: number,
			column: number
		},
		// The currently active state of this instance.
		state: number,
		// Whether or not this event was triggered as part of a Multi Action.
		isInMultiAction: boolean
	}
}
```

### keyUp

Fired on keypad key up.

**Received by:** Plugin

```ts
{
	event: string = "keyUp",
	action: string,
	context: string,
	device: string,
	payload: {
		settings: any,
		coordinates: {
			row: number,
			column: number
		},
		state: number,
		isInMultiAction: boolean
	}
}
```
