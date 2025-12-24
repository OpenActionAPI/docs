# Applications

### applicationDidLaunch

Fired when an application that is registered for monitoring in the plugin manifest is launched.

**Received by:** Plugin

```ts
{
	event: string = "applicationDidLaunch",
	payload: {
		application: string
	}
}
```

### applicationDidTerminate

Fired when an application that is registered for monitoring in the plugin manifest is terminated.

**Received by:** Plugin

```ts
{
	event: string = "applicationDidTerminate",
	payload: {
		application: string
	}
}
```
