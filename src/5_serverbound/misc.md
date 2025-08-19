# Miscellaneous

### openUrl

Used to open a fully-qualified URL in the user's default browser.

**Sent by:** Plugin, Property inspector

```ts
{
	event: string = "openUrl",
	payload: {
		url: string // e.g. "https://example.com/"
	}
}
```

### logMessage

Used to log a debug message to a log file. It is more strongly advised for plugin developers to handle logging on their own.

**Sent by:** Plugin

```ts
{
	event: string = "logMessage",
	payload: {
		message: string
	}
}
```

### showAlert

Used to show a temporary alert indicator on the instance.

**Sent by:** Plugin

```ts
{
	event: string = "showAlert",
	context: string
}
```

### showOk

Used to show a temporary checkmark indicator on the instance.

**Sent by:** Plugin

```ts
{
	event: string = "showOk",
	context: string
}
```
