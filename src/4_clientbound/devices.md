# Devices

### deviceDidConnect

Fired when a device is connected.

The Stream Deck software supplies an additional field, an integer to designate the model of Stream Deck in use.

**Received by:** Plugin

```ts
{
	event: string = "deviceDidConnect",
	device: string,
	deviceInfo: {
		name: string,
		size: {
			rows: number,
			columns: number
		}
	}
}
```

### deviceDidDisconnect

Fired when a device is disconnected.

The Stream Deck software supplies an additional field, an integer to designate the model of Stream Deck in use.

**Received by:** Plugin

```ts
{
	event: string = "deviceDidDisconnect",
	device: string
}
```
