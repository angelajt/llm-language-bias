# llm-language-bias

## notebooks

### Llama 3.1

[llama 3.1](https://github.com/angelajt/llm-language-bias/blob/main/llama_3.1.ipynb)
Querying the Llama 3.1 8B Instruct model.
- English
- Spanish

[llama 3.1 base model](https://github.com/angelajt/llm-language-bias/blob/main/llama_3.1_base_model.ipynb)
Querying the Llama 3.1 8B base model, by letting it predict the next character after the prompt.
- English
- Spanish
- Mandarin (Llama 3.1 does not support Mandarin, so results are messy)

[llama 3.1 open ended](https://github.com/angelajt/llm-language-bias/blob/main/llama_3.1_open_ended.ipynb)
Instead of forcing the 8B Instruct model to select a choice without including any other text, let it explain its answer. This is to compare whether or not forced-choice and open-ended prompts give different answers.
- English
- Spanish

[llama 3.1 reverse](https://github.com/angelajt/llm-language-bias/blob/main/llama_3.1_reverse.ipynb)
Reverse the scale, to test whether e.g. the 8B Instruct model chooses "0" instead of "5", or if it simply prefers to respond with higher numbers.
- English
- Spanish

### Qwen2

[qwen2](https://github.com/angelajt/llm-language-bias/blob/main/qwen2.ipynb)
This model supports Chinese (Mandarin). Also, we can compare the results to those of models developed in the US (GPT, Llama...).
- English
- Spanish
- Mandarin

## next steps

- One priority is to find existing studies of English-, Spanish-, and Mandarin-speakers who have completed the MFQ, and compare these to each of the models.
- TODO discuss more
