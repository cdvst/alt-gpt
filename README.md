[![Netlify Status](https://api.netlify.com/api/v1/badges/781e6c88-32f4-45d2-add3-7d3757661a7a/deploy-status)](https://app.netlify.com/sites/alt-gpt/deploys)

# Alt-GPT
Multi-model and multi-vendor playground for developing ChatGPT plugins (for OAI and other LLMs) 

<img width="1164" alt="image" src="https://user-images.githubusercontent.com/246724/228085849-b3cdf285-3414-4f75-9e86-6620bb863d55.png">

## Features:
- 🌟 Plugins: Support AI plugins, discover and use public publics and develop locally your new plugin! 
- BYOK: Bring-your-own-key. Soon: Use API-keys from multiple vendors.
- Privacy: All logic and network requests are on client-side, including usage of your API keys.
- Local Persistance: Messages and settings are saved in locally on your device's LocalStorage

## Caveats:
1. Plugins support in Langchain is still experimental, buggy and slow
1. Langchain doesn't support client-side processing, so api keys has to be sent and handled on a backend.
1. Limited to a single plugin at a time.

## Develop
### Setup
1. Clone locally
1. Run `$ yarn install`

### Start web:
1. Run `$ yarn watch`
2. Open browser on `http://0.0.0.0:3010/`

### Optional: Start plugin-executer service:
1. Run `$ cd functions && yarn serve`
2. Set in your browser devtools `localStorage.isLocal = true`, to let the FE request your local function.

## How it works:
<img width="750" alt="image" src="https://user-images.githubusercontent.com/246724/228149571-d2059e02-78d1-4724-8be8-8513feddbd2f.png">

When using the playground without plugins selected, everything is client-side only, no communication other than with the LLM provider.
When selecting a plugin, due to current limitation of Langchain, the communication is sent through BE, by default we've deployed a simple serverless function to GCP ([source here](/functions)). You can run your own local instance if your want to avoid this network travel.

## Creating new API keys
It is recommended to create a dedicated key so it could be revoked easily later.
- **OpenAI**: Create new api key [here](https://platform.openai.com/account/api-keys)
- [TBD]


## Contribute

Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first and submit a Pull Request after Fork this repository.

## Contact
Please use GitHub [Issues](https://github.com/Feedox/alt-gpt/issues?q=is%3Aissue+is%3Aopen+sort%3Aupdated-desc) to contact us.

