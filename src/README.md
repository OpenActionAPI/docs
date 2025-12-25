# OpenAction

### Welcome!

OpenAction is an API for developers looking to create custom actions for programmable control surfaces, like the Elgato Stream Deck, Tacto, and other similar products.

OpenAction is backwards-compatible with the Stream Deck SDK, which already allows developers to work in any programming language that supports WebSockets. Unlike the SD SDK, however, it aims to work on any operating system, and is designed for use with any device.

### Ecosystem

Generally speaking, developers working with the API to create their own custom actions will be creating OpenAction clients: plugins and their property inspectors. You can browse a catalogue of open source plugins on the [OpenAction Marketplace](https://marketplace.rivul.us). Once released on the marketplace, users can use these plugins with an OpenAction server.

The reference implementation of an OpenAction server is [OpenDeck](https://github.com/nekename/OpenDeck), an open source project that can be extended to support a variety of devices, and runs on all three major desktop operating systems. [Tacto](https://tacto.rivul.us) is a derivative of OpenDeck, from the same developer, with a focus on using mobile devices instead of dedicated hardware.

![](https://tacto.rivul.us/screenshots.png)

Provided that your plugin doesn't use extended features of the OpenAction API that aren't supported by the Stream Deck SDK, your plugin should also work with both the Elgato Stream Deck software and third-party software like Mirabox Stream Dock.

### Recommended development workflow

Although the OpenAction API preserves the flexibility of being able to use any programming language, the recommended workflow for new plugin developers incorporates the [Rust](https://rust-lang.org/) programming language using the official [OpenAction crate](https://github.com/OpenActionAPI/rust) (library).

For building property inspectors, the most ergonomic approach is either to use the [Svelte](https://svelte.dev/) web framework using the official [OpenAction Svelte library](https://github.com/OpenActionAPI/svelte-pi), or Elgato's [SDPI Components](https://sdpi-components.dev) framework. Using Svelte is recommended for more involved property inspectors, as it allows for better reactivity and easier reuse of components.

### Next steps

This documentation site is split into multiple sections. The initial section covers the basics of the API, applicable to users of all programming languages, followed by a section that covers the basics of using the Rust crate, and then a final section containing a technical reference on the supported events.

The next page covers the basic concepts of the API, that all plugin developers should become familiar with.
