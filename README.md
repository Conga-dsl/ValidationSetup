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

## CONGA Validator
The CONGA DSL includes model validation rules, which every CONGA model should satisfy. The table summarizes the validation rules currently supported by CONGA. The rules has two types of severity, error and warnings. Warnings can also be classified in Best Practice (BP), Heuristic (H), Missing Element (ME), Malformed element (MF) and Unused Element (UE). 

| **Id**  | **Validation rule**                                                                                  | **Severity** |
|---------|------------------------------------------------------------------------------------------------------|:------------:|
| **G1**  | Names of intents, actions, entities, and parameters should be unique                                 |     error    |
| **G2**  | The language of the element (intent, action, entity) must be included within the chatbot languages   |     error    |
| **G3**  | There cannot be two LanguageInputs of the same language in the same element (intent, action, entity) |     error    |
| **G4**  | Different flow paths cannot start with the same intent                                               |     error    |
| **G5**  | There should be a referencing HTTPRequest before each HTTPResponse                                   |     error    |
| **G6**  | Reference “back to” must point to an element in the same path, at a previous position                |     error    |
| **G7**  | Parameters in the training phrase must be defined in the same intent                                 |     error    |
| **G8**  | All entries of the entity should be of the same type                                                 |     error    |
| **G9**  | There should be one LanguageInput per chatbot language                                               | warning (ME) |
| **G10** | Regex syntax must be well-formed                                                                     | warning (MF) |
| **G11** | Loops should have some terminating branch                                                            |  warning (H) |
| **G12** | Defined entities should be used in some parameter                                                    | warning (UE) |
| **G13** | Intents should be used in some flow                                                                  | warning (UE) |
| **G14** | Mandatory parameters should be used in some training phrase                                          | warning (UE) |
| **G15** | The language intent must contain at least three training phrases                                     | warning (BP) |
| **G16** | Two training phrases should not be equal in different intents                                        | warning (BP) |
| **G17** | Two training phrases should not be equal in the same intent                                          | warning (BP) |
| **G18** | If the phrase has a text parameter, it should have more content                                      | warning (BP) |
| **G19** | The chatbot should have a fallback intent                                                            | warning (BP) |
| **G20** | Mandatory parameters should have prompts                                                             | warning (BP) |
