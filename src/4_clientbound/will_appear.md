# Will appear

### willAppear

Fired when the user switches to a profile containing this action, or a new instance of this action is created.

**Received by:** Plugin

```ts
{
	event: string = "willAppear",
	action: string,
	context: string,
	device: string,
	payload: {
		settings: any,
		coordinates: {
			row: number,
			column: number
		},
		controller: string,
		state: number,
		isInMultiAction: boolean
	}
}
```

### willDisappear

Fired when the user switches from a profile containing this action, or an instance of this action is removed.

**Received by:** Plugin

```ts
{
	event: string = "willDisappear",
	action: string,
	context: string,
	device: string,
	payload: {
		settings: any,
		coordinates: {
			row: number,
			column: number
		},
		controller: string,
		state: number,
		isInMultiAction: boolean
	}
}
```
