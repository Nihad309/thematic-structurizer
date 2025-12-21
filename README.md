# thematic-structurizer
[![PyPI version](https://badge.fury.io/py/thematic-structurizer.svg)](https://badge.fury.io/py/thematic-structurizer)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Downloads](https://static.pepy.tech/badge/thematic-structurizer)](https://pepy.tech/project/thematic-structurizer)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue)](https://www.linkedin.com/in/eugene-evstafev-716669181/)


Thematic Structurizer is a Python package designed to process user-provided text related to historical or thematic content—such as summaries, descriptions, or analyses of topics like persuasion techniques from antiquity—and extract structured, pattern-validated data. It leverages large language models (LLMs) to generate responses in a predefined format, ensuring consistency and reliability through regex validation and retry mechanisms.

## Installation

Install the package via pip:

```bash
pip install thematic_structurizer
```

## Usage

Here's an example of how to use the package:

```python
from thematic_structurizer import thematic_structurizer

# Example user input
user_input = "Describe the persuasion techniques used by Cicero in ancient Rome."

# Calling the function with default LLM (ChatLLM7)
response = thematic_structurizer(user_input)
print(response)
```

## Custom LLM Support

The package uses `ChatLLM7` from `langchain_llm7` by default. You can provide your own language model instance to customize the behavior. Supported models include those from OpenAI, Anthropic, Google Generative AI, etc.

### Example with a custom LLM:

```python
from langchain_openai import ChatOpenAI
from thematic_structurizer import thematic_structurizer

llm = ChatOpenAI()
response = thematic_structurizer(user_input, llm=llm)
```

### Alternatively, using other providers:

```python
from langchain_anthropic import ChatAnthropic
from thematic_structurizer import thematic_structurizer

llm = ChatAnthropic()
response = thematic_structurizer(user_input, llm=llm)
```

## API Key Management

For the default `ChatLLM7`, you can set your API key via environment variable:

```bash
export LLM7_API_KEY='your_api_key'
```

or pass it directly:

```python
response = thematic_structurizer(user_input, api_key='your_api_key')
```

To obtain a free API key, register at [https://token.llm7.io/](https://token.llm7.io/).

## Function Details

```python
def thematic_structurizer(
    user_input: str,
    api_key: Optional[str] = None,
    llm: Optional[BaseChatModel] = None
) -> List[str]:
```

- `user_input`: The text to process, such as a description, summary, or analysis.
- `llm`: An optional language model instance; defaults to `ChatLLM7`.
- `api_key`: Optional string; API key for `ChatLLM7`.

This function processes the input, invokes the LLM, and returns a list of extracted data that match the predefined pattern validation.

## License

This project is maintained by Eugene Evstafev. For issues or contributions, please visit [https://github.com/chigwell/thematic-structurizer](https://github.com/chigwell/thematic-structurizer).

## Contact

- Email: hi@eugene.plus
- GitHub: [chigwell](https://github.com/chigwell)