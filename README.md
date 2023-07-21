# Validation Setup
[CONGA](https://saraperezsoler.github.io/CONGA/) is a MDE solution to implement chatbots. It consists of:
- A DSL to define chatbot models
- A code generator for several chatbot development tools
- A recommender that suggests the best development tool based on the chatbot definition and a questionnaire about the technical requirement
- A parser from chatbot tools to the CONGA DSL
The repository contains a dataset used in evaluations of the CONGA DSL validator of 291 chatbots from 4 different sources: Code repositories like Github, predefined chatbots from the Dialogflow and Rasa platforms, as well as predefined bots from other platforms, like [Kommunicate](https://www.kommunicate.io/). The following table summarizes the content of the dataset.


| **Technology** | **Source**  | **#Chatbots** |
|----------------|-------------|---------------|
| Dialogflow     | Prebuild    | 17            |
| Dialogflow     | Github      | 116           |
| Dialogflow     | Kommunicate | 7             |
| Rasa           | Prebuild    | 3             |
| Rasa           | Github      | 148           |
|                | **Total**   | 291           |

The chatbots are divided into two folders, Dialogflow and Rasa, depending on the technology to which the chatbot belongs. The folders contain the source of each chatbot, the CONGA's models (XMI file) and DSLs (Bot file) for each chatbot and a table with the results of the evaluation performed with CONGA DSL validator.
