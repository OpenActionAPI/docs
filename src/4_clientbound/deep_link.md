# Deep link

### didReceiveDeepLink

Fired when a deep link URL matching a format for sending messages to the plugin is opened.

The URL formats that can trigger this event are
- `openaction://plugins/message/<PLUGIN_DIRECTORY_NAME>/<MESSAGE_CONTENT>[?openaction=hidden]` and
- `streamdeck://plugins/message/<PLUGIN_UUID>/<MESSAGE_CONTENT>[?streamdeck=hidden]`,

where the optional query parameter specifies that the OpenAction server's window should not be brought to the foreground when the deep link is opened.

**Received by:** Plugin

```ts
{
	event: string = "didReceiveDeepLink",
	payload: {
		url: string
	}
}
```
