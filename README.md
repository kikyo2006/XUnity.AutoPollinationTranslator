# XUnity.AutoPollinationTranslator

A translation endpoint for [XUnity.AutoTranslator](https://github.com/bbepis/XUnity.AutoTranslator) that uses [Pollinations AI](https://pollinations.ai/) to provide free, uncensored, and high-quality translations for games.

This project is a fork of [XUnity.AutoChatGptTranslator](https://github.com/joshfreitas1984/XUnity.AutoChatGptTranslator) optimized for the Pollination AI service.

## Features

- **Free & Uncensored**: Uses Pollinations AI which does not have restrictive content filters, making it ideal for various game contexts.
- **High Performance**: Optimized JSON output handling for stable and clean translations.
- **Parallel Requests**: Supports efficient translation batches.
- **Customizable**: Full control over system prompts, models, and temperature.

## Installation Instructions

1. **Build the Assembly**: Compile the project or obtain the `XUnity.AutoPollinationTranslator.dll`.
2. **Install AutoTranslator**: Ensure you have [XUnity.AutoTranslator](https://github.com/bbepis/XUnity.AutoTranslator) installed in your game.
3. **Deploy the Plugin**: Place `XUnity.AutoPollinationTranslator.dll` into the `<GameDir>/ManagedData/Translators` directory (where other translator DLLs are located).
4. **Configure the Service**: Update your `AutoTranslatorConfig.ini` file located in `<GameDir>/AutoTranslator`.

## Configuration (`AutoTranslatorConfig.ini`)

Add or update the following sections in your configuration file:

```ini
[Service]
Endpoint=PollinationTranslate

[Pollination]
; Base URL for the service. Default is text.pollinations.ai
BaseUrl=https://gen.pollinations.ai/v1/chat/completions

; Model to use (options: openai, grok, mistral, p1, etc.)
Model=openai

; Your custom translation prompt
Prompt=Translate the following text to English, maintaining the original tone and context.

; Delay between translation requests in seconds (default is 1.0)
TranslateDelay=1.0

; Random seed for deterministic results (-1 for random)
Seed=-1

; Creativity level (0.0 = literal, 1.0 = balanced, 2.0 = creative)
Temperature=1.0

; Max retries for failed or truncated translations
MaxRetries=3

; Maximum tokens per response
MaxTokens=2000

; Enable debug logging in the Xua console
Debug=false
```

## Credits

- **Original Author**: [joshfreitas1984](https://github.com/joshfreitas1984) for the initial ChatGPT translator implementation.
- **Service Provider**: [Pollinations AI](https://pollinations.ai/) for the underlying AI infrastructure.
