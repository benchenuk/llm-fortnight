# LLM Fortnight
This is a space for keeping releveant notes and documents produdced along the way of testing and using different locally deployed LLMs. 

## Models
A handful of models are just small enough to run on consumer computers to allow exploring and testing latest LLM capabilities. 
The open source community continues releasing more and more powerful and speedy models. I'd say these models are not only fit for prototyping locally, with careful selection and configuration, also competent for basic assistive tasks.       

- DeepSeek R1 (up to 32B Distill)
- Qwen2.5 14B Coder
- Qwen2.5 14B 1M
- QwQ 32B
- Phi4 / Phi4-Mini
- Gemma 3

## Stack
- GitHub Copilot
- Gemini Code Assist
- CodeGPT
- Roo Code
- VS Code
- SearXNG
- Open WebUI
- LM Studio
- Ollama
- 32G RAM
- Apple Silicon M4

## Prompts
Not that long before "vibe doing" things became trendy, there was proper term for it - "prompt engineering". 
It is a technique for engineer-minded user to instruct LLM exactly the way you want it respond. 
It makes noticeable and substantial differences to the quality of chat outputs, given the same capability of the model under test. 

Like the publicly available benchmarks, for every new (version) of model, a same set of questions are sent to the model to "vibe check" the performance and character of the model. 

And then this process will repeat with every parameter or system prompt change, until a satisfactory combination is found.  


## Current Lineup
| Task | Base | Custom Model| Comments |
| ----------- | ----------- | ----------- | ----------- |
| General | **Gemini3 12B** | gemini3-flash | Summarization, fast, decent reasoning |
|         | Phi4 Mini | phi4-flash | Very fast, logic |
| Complex | **DeepSeek 14B** | deepseek-reason| Balanced |
|         | QwQ 32B | qwq-32b | Full but slow |
| Code    | **Qwen2.5 Coder 14B** | [TBD] | [TBD] |
| Other(Agent) | Mistral Small 3 24B | mistral-agent | [TBD]


## References
- [Ollama Models](https://ollama.com/search)
- [LM Studio Models](https://lmstudio.ai/models)
- [HuggingFace](https://huggingface.co)
- [Gemma3 @Ollama](https://ollama.com/library/gemma3:12b)
- [Phi-4 Mini @Ollama](https://ollama.com/library/phi4-mini)
- [Phi-4 @Ollama](https://ollama.com/library/phi4:14b)
- [Phi-4 @HuggingFace](https://huggingface.co/collections/microsoft/phi-4-677e9380e514feb5577a40e4)
- [Mistral Small3 @Ollama](https://ollama.com/library/mistral-small:24b)
- [DeepSeek-R1 @HugginFace](https://huggingface.co/deepseek-ai/DeepSeek-R1)
- [Qwen @HuggingFace](https://huggingface.co/Qwen)
- [QwQ @GitHub](https://github.com/QwenLM/QwQ)
- [SearXNG @Open WebUI](https://docs.openwebui.com/tutorials/web-search/searxng/)


## TO DO
- DeepSeek Distilled Versions
- Gemma3 Flash
- Open WebUI + Searxng / Duckduckgo
- Coder Prompt
- LM Studio vs. Ollama
- Phi4 Flash
- Preplexica
- Local Knowledge Base / RAG
- Agent frameworks / LangGraph