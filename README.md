 # Chat AI Personas Repository

This repository contains JSON files that define various personas for use in [Chat AI](https://chat-ai.academiccloud.de). Each JSON file includes the system prompt, settings, and conversations, allowing you to easily load a persona into Chat AI with a simple link.

## Table of Contents

- [Introduction](#introduction)
- [Usage](#usage)
- [File Structure](#file-structure)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This repository is designed to provide a collection of pre-defined personas that can be used to enhance the conversational capabilities of chat AI applications. Each persona is defined in a JSON file, making it easy to integrate into your chat AI system.

## Usage

To use a persona in Chat AI, simply add the link to the JSON file in the import parameter of the URL. Here's an example:

```
https://chat-ai.academiccloud.de/chat?import=https://raw.githubusercontent.com/gwdg/chat-ai-personas/refs/heads/main/gwdg-support.json
```

## File Structure

The repository is organized as follows:

```
chat-ai-personas/
├── examples/
│   └── ...
├── research/
│   └── ...
├── arcanas/
│   └── ...
├── translation/
│   └── de_en.json
│   └── en_de.json
├── README.md
├── assistant.json
├── gwdg-support.json
└── LICENSE
```

- `examples/`: Contains some general examples
- `research/`: Contains personas that are useful in research.
- `arcanas/`: Contains personas with knowledge bases (RAG).
- `translation/`: Contains personas for text translation.
- `README.md`: This file.
- `LICENSE`: The license for this repository.

## JSON Structure of Personas

Persona files have the following structure:
```js
{
  "title": "Title",
  "subtitle": "Subtitle",
  "model-name": "AI model name, must be supported by Chat AI",
  "model": "AI model, must be supported by Chat AI",
  "temperature": 0.2, // should be 0 for arcanas
  "top_p": 0.2, // should be 0 - 0.05 for arcanas
  "messages": [
    {
      "role": "system",
      "content": "This is a system prompt."
    },
    { // optional
      "role": "info",
      "content": "This message is only visible to the user."
    }
  ],
  "arcana": { // optional, only for RAG
    "id" : "username/arcana-name"
  }
}
```

## Contributing

Contributions are welcome! If you have a new persona you'd like to add, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature (`git checkout -b feature/new-persona`).
3. Add your JSON file to the corresponding directory.
4. Commit your changes (`git commit -m 'Add new persona'`).
5. Push to the branch (`git push origin feature/new-persona`).
6. Open a Pull Request.

Please ensure your JSON files follow the structure outlined in the existing files.

## Notable Personas

- [assistant](https://chat-ai.academiccloud.de/chat?import=https://raw.githubusercontent.com/gwdg/chat-ai-personas/refs/heads/main/assistant.json):
General assistant
- [gwdg-support](https://chat-ai.academiccloud.de/chat?import=https://raw.githubusercontent.com/gwdg/chat-ai-personas/refs/heads/main/gwdg-support.json): GWDG Support Bot
- [research/glossary](https://chat-ai.academiccloud.de/chat?import=https://raw.githubusercontent.com/gwdg/chat-ai-personas/refs/heads/main/research/glossary.json): Create short definitions for terms
- [research/spellfix](https://chat-ai.academiccloud.de/chat?import=https://raw.githubusercontent.com/gwdg/chat-ai-personas/refs/heads/main/research/spellfix.json): Check for errors in text by regeneration and comparison
- [translation/de_en](https://chat-ai.academiccloud.de/chat?import=https://raw.githubusercontent.com/gwdg/chat-ai-personas/refs/heads/main/translation/de_en.json): Simple German to English translator
- [translation/en_de](https://chat-ai.academiccloud.de/chat?import=https://raw.githubusercontent.com/gwdg/chat-ai-personas/refs/heads/main/translation/en_de.json): Simple English to German translator

## License

This project is licensed under the GPLv3 License - see the [LICENSE](LICENSE) file for details.

---

Thank you for using the Chat AI Personas repository! If you have any questions or need further assistance, please feel free to open an issue or contact the repository maintainers.
