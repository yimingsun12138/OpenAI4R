# OpenAI4R

OpenAI is an artificial intelligence research laboratory founded by a group of technology leaders in 2015, with the aim of advancing digital intelligence technology for the benefit of humanity as a whole. OpenAI conducts research in various areas of artificial intelligence, including natural language processing, robotics, and reinforcement learning. It has developed several powerful AI models, such as GPT (Generative Pre-trained Transformer) and DALL-E, which can generate human-like language and images from textual descriptions.

The development of the OpenAI4R R package, is aimed to enable a clear and intuitive calling of OpenAI's powerful AI models within the R language.

## Install

Execute in R:

```{R}
devtools::install_github('yimingsun12138/OpenAI4R')
```

To install the under-development version, execute:

```{R}
devtools::install_github('yimingsun12138/OpenAI4R',ref = 'dev')
```

## Notice

OpenAI4R now provides ChatGPT API only. More APIs will be added later.

## Usage

Load package and set up authentication:

```{R}
library(OpenAI4R)

# Input your own OpenAI API key and organization.
Auth_OpenAI(key = readLines('/content/script/openai_API_key'))
```

A global variable named `OpenAI_API_key` will appear in the current environment.

### Chat model

For chat model, initialize a chat session first. You can post your first command here as 'system' to set the global settings, modify the parameters of the chat model, or import an existing chat session to continue the conversation.

```{R}
chat <- Init_chat_session()
```

Then, you can use this initialized function to have a continuous conversation. Here is an example:

```{R}
> chat('Play a game with me. generate a number between 1 to 10 and i will guess it. If I am wrong, tell me how to adjust')
ChatGPT:
Sure, I can generate a random number between 1 to 10. Alright, I've got one in mind. Go ahead and make your first guess!

> chat('5')
ChatGPT:
Sorry, your guess was incorrect. The number I generated was less than 5. Please guess again, but this time try a lower number!

> chat('3')
ChatGPT:
Great job! You guessed it correctly. The number I was thinking of was indeed 3. Congratulations!

> chat('That is fun')
ChatGPT:
I'm glad you enjoyed the game! Feel free to play again or try out some other games. Let me know if you need any help.
```

You can also modify the model parameters during the conversation and export the conversation history. Refer to `?chat_func_char` for more details.

## Future Plan

-   Add more OpenAI APIs in this package.

-   More detailed document and guidance.

-   Use a universal function to initialize all APIs, when more APIs are added in the future.
