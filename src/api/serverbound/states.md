# States

### setTitle

Used to set the title of an instance.

**Sent by:** Plugin

```ts
{
	event: string = "setTitle",
	context: string,
	payload: {
		title: string,
		// 0: Both hardware and software, 1: Hardware only, 2: Software only
		target: number = 0,
		// 0-based index specifying the state to be modified.
		// If not set, the title will be applied to all states.
		state: number | null
	}
}
```

### setImage

Used to set the image of an instance.

**Sent by:** Plugin

```ts
{
	event: string = "setImage",
	context: string,
	payload: {
		// A base-64 data URL encoded image.
		image: string,
		// 0: Both hardware and software, 1: Hardware only, 2: Software only
		target: number = 0,
		// 0-based index specifying the state to be modified.
		// If not set, the image will be applied to all states.
		state: number | null
	}
}
```

### setState

Used to switch an action to a state.

**Sent by:** Plugin

```ts
{
	event: string = "logMessage",
	payload: {
		// 0-based index specifying the state to be switched to.
		state: number
	}
}
```
