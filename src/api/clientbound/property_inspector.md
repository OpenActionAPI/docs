# Property inspector

### sendToPlugin

Fired when the property inspector uses the `sendToPlugin` event.

**Received by:** Plugin

```ts
{
	event: string = "sendToPlugin",
	action: string,
	context: string,
	payload: any
}
```

### sendToPropertyInspector

Fired when the plugin uses the `sendToPropertyInspector` event.

**Received by:** Property inspector

```ts
{
	event: string = "sendToPropertyInspector",
	action: string,
	context: string,
	payload: any
}
```

### propertyInspectorDidAppear

Fired when an action is selected and its property inspector appears.

**Received by:** Plugin

```ts
{
	event: string = "propertyInspectorDidAppear",
	action: string,
	context: string,
	device: string
}
```

### propertyInspectorDidDisappear

Fired when an action is deselected and its property inspector disappears.

**Received by:** Plugin

```ts
{
	event: string = "propertyInspectorDidDisappear",
	action: string,
	context: string,
	device: string
}
```
