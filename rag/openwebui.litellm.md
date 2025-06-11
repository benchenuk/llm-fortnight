# Open WebUI with LiteLLM
LiteLLM is a proxy for LLMs, allowing you to proxy LLMs through API, either locally by Ollama or remotely via third party API endpoint. The API interface is compatible with OpenAI. This allows you to access different LLMs via a unified API interface. 

In Open WebUI, this means you can configure to use LiteLLM as direct connection, so that when a chat is initiated, the desired model will be proxied through. 

## LiteLLM Configuration 

### Add New Model to LiteLLM 

LiteLLM runs on `http://localhost:4000/` and the admin dashboard can be accessed at `http://localhost:4000/ui`. To add a new model, use the dashboard by navigating to the "Models" section and clicking on the "Add Models" tab. 

The following instructions takes the Free DeepSeek V3 for example. 

| Field | Value|
|---|---|
| **Provider** | OpenRouter|
| **LiteLLMModel** | openrouter/deepseek/deepseek-chat-v3 |
| **Public Name** | openrouter/deepseek/deepseek-chat-v3-0324:free |
| **API Key** | (secret key) |

### Add New Key to LiteLLM 

It is worth adding a new key for the dedicated OpenRouter access. Navigate to the "`Virtual Keys`" section and clicking on the "`Create New Keys`". Then the new model will become available to choose.

| Field | Value|
|---|---|
| **Key Name** | (Meaningful name) |
| **Models** | openrouter/deepseek/deepseek-chat-v3-0324:free |

Upon saving, a new key will be created and ready to use. 

## Open WebUI Configuration
### Enable Direct Connection

Make sure the "`Direct Connections`" option is enabled in the `Admin settings -> Connections`.

### Add Direct Connection for LiteLLM

Add a new connection using the following parameters:
| Field | Value|
|---|---|
| **URL** | http://localhost:4000/v1 |
| **Key** | (Keey created on LiteLLM) |
| **Prefix ID** | openrouter |

This will cause LiteLLM to query all available models under the provided API key. 

### Select Model in OpenWebUI

In a new chat session, select the LiteLLMmodel you want to use from the dropdown menu. In this case, it should be `openrouter/deepseek/chat-v3-0324:free`. The chat will now proxy through LiteLLM and use OpenRouter. 


