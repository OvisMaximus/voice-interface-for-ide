# voice-interface-for-ide

![Build](https://github.com/OvisMaximus/voice-interface-for-ide/workflows/Build/badge.svg)
[![Version](https://img.shields.io/jetbrains/plugin/v/PLUGIN_ID.svg)](https://plugins.jetbrains.com/plugin/PLUGIN_ID)
[![Downloads](https://img.shields.io/jetbrains/plugin/d/PLUGIN_ID.svg)](https://plugins.jetbrains.com/plugin/PLUGIN_ID)


<!-- Plugin description -->
Use the microphone of your computer to enter and edit code in your IDE and trigger their functions by natural language.
<!-- Plugin description end -->

## Template ToDo list
- [x] Create a new [IntelliJ Platform Plugin Template][template] project.
- [ ] Get familiar with the [template documentation][template].
- [ ] Adjust the [pluginGroup](./gradle.properties), [plugin ID](./src/main/resources/META-INF/plugin.xml) and [sources package](./src/main/kotlin).
- [ ] Adjust the plugin description in `README` (see [Tips][docs:plugin-description])
- [ ] Review the [Legal Agreements](https://plugins.jetbrains.com/docs/marketplace/legal-agreements.html?from=IJPluginTemplate).
- [ ] [Publish a plugin manually](https://plugins.jetbrains.com/docs/intellij/publishing-plugin.html?from=IJPluginTemplate) for the first time.
- [ ] Set the `PLUGIN_ID` in the above README badges.
- [ ] Set the [Plugin Signing](https://plugins.jetbrains.com/docs/intellij/plugin-signing.html?from=IJPluginTemplate) related [secrets](https://github.com/JetBrains/intellij-platform-plugin-template#environment-variables).
- [ ] Set the [Deployment Token](https://plugins.jetbrains.com/docs/marketplace/plugin-upload.html?from=IJPluginTemplate).
- [ ] Click the <kbd>Watch</kbd> button on the top of the [IntelliJ Platform Plugin Template][template] to be notified about releases containing new features and fixes.

## Installation

- Using IDE built-in plugin system:
  
  <kbd>Settings/Preferences</kbd> > <kbd>Plugins</kbd> > <kbd>Marketplace</kbd> > <kbd>Search for "voice-interface-for-ide"</kbd> >
  <kbd>Install Plugin</kbd>
  
- Manually:

  Download the [latest release](https://github.com/OvisMaximus/voice-interface-for-ide/releases/latest) and install it manually using
  <kbd>Settings/Preferences</kbd> > <kbd>Plugins</kbd> > <kbd>⚙️</kbd> > <kbd>Install plugin from disk...</kbd>


---
Plugin based on the [IntelliJ Platform Plugin Template][template].

[template]: https://github.com/JetBrains/intellij-platform-plugin-template
[docs:plugin-description]: https://plugins.jetbrains.com/docs/intellij/plugin-user-experience.html#plugin-description-and-presentation

## Vision

An AI / LLM based driver for lonly pair programming sessins. 

The driver in a car rally is the person who operates the car, while the navigator sits in the passenger seat and
advises the driver on how best to proceed to reach their destination. The driver is responsible for the safety of
the car and the passengers and must be able to react to any situation that may arise on the road.
The navigator is responsible for keeping the driver on the correct route and advising of any hazards or other
information.

In pair programming, the driver is the programmer who is typing at the keyboard. By focusing on the "mechanics" of
coding, the driver is able to concentrate on the syntax and semantics of the language, and can be more objective
about the work. The navigator reviews each line of code as it is typed in, checking for errors and thinking
strategically about the direction of the work.

Another metaphor of the driver is a "smart voice controlled keyboard" that is able to type code on a higher
abstraction level than a simple speech to text system.

Using LLMs (Language Models) and AI (Artificial Intelligence) to solve a problem in a new to me programming language
or library significantly raise the speed to get things working. Instead of searching for web pages addressing the
topic and selecting relevant results one gets relevant and mostly correct hints including code from the LLM.

The drawback are the 'hallucinations' of LLMs.
When the LLM insists on using a parameter of a signature, that neither exists nor ever existed, I feel my time
wasted: I start by asking the LLM how a certain goal can be programmatically achieved, implementing the suggestion
of the LLM, let it compile and/or run, rephrasing the error message of the compiler and incorporating it
into the query to the LLM, changing the code with the new suggestion of the LLM and repeating these steps until the
code compiles, tests run green and the code does what I want it to do. What if these steps could be automated?

That's the vision of this plugin: Let me talk to my IDE as if there is a pair programming partner sitting next to
me in the role of the driver who is familiar with the used language and libraries. They also know things I
don't know so their wisdom becomes part of the commonly produced code. The driver knows that we perform TDD and
reminds me to stick to good habits when I feel tempted to shortcut something. After a Test is implemented and
compiles, we both intend to create production code that satisfies the test. The driver starts build and runs the
test without waiting for me to ask for it. When the compile fails due to a syntax error, they can fix them on their
own. Our plugin shall implement this feedback cycle with the LLM thus saving me from the tedious task of passing
messages from the LLM to the IDE and back.
