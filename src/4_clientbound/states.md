# States

### titleParametersDidChange

Fired when the user changes the title parameters of an action.

```ts
{
	event: string = "titleParametersDidChange",
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
		title: string,
		titleParameters: {
			fontFamily: string,
			fontSize: number,
			fontStyle: string,
			fontUnderline: boolean,
			showTitle: boolean,
			titleAlignment: string,
			titleColor: string
		}
	}
}
```
