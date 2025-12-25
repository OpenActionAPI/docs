# Encoder

### dialRotate

Fired on encoder dial rotate or encoder slider move.

**Received by:** Plugin

```ts
{
	event: string = "dialRotate",
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
		// For a dial, positive value signifies clockwise rotation, and a negative value signifies anticlockwise rotation.
		// The lowest position is set as 0, and highest position is set as 192.
		ticks: number,
		pressed: boolean
	}
}
```

### dialDown

Fired on encoder dial down.

**Received by:** Plugin

```ts
{
	event: string = "dialDown",
	action: string,
	context: string,
	device: string,
	payload: {
		settings: any,
		coordinates: {
			row: number,
			column: number
		},
		controller: string
	}
}
```

### dialUp

Fired on encoder dial up.

**Received by:** Plugin

```ts
{
	event: string = "dialUp",
	action: string,
	context: string,
	device: string,
	payload: {
		settings: any,
		coordinates: {
			row: number,
			column: number
		},
		controller: string
	}
}
```
