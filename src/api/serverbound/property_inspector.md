# Property inspector

### sendToPlugin

Fired by a property inspector to send a message to the plugin.

**Sent by:** Property inspector

```ts
{
	event: string = "sendToPlugin",
	action: string,
	context: string,
	payload: any
}
```

### sendToPropertyInspector

Fired by the plugin to send a message to a property inspector.

**Sent by:** Plugin

```ts
{
	event: string = "sendToPropertyInspector",
	action: string,
	context: string,
	payload: any
}
```
