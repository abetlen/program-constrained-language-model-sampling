# Program Constrained Transformers

> The aim of this project is to investigate the use of program constraints on pre-trained transformers to improve their ability to generate structured text as output.

Language models can accurately predict the next token in a sequence.
Unfortunately generated text is not necessarily structured in a way that can be utilised by other programs.
For example, a language model that extracts json objects from unstructured text may fail to produce a valid json object by adding additional trailing commas or introducing comments.

We propose a simple method to constrain the tokens that can be sampled by a language model by using an external program to decide which tokens in the vocabulary are valid at a given point in the sequence.
We then force the transformer to *only* sample over these valid tokens.

# Overview

![Constrained Transformers](./overview.drawio.svg)

- **Transformer**: Any pre-trained transformer model, such as BERT, GPT-2, or T5.
- **Program**: A program that takes a sequence of tokens as input and can determine if a subsequent token is valid.

## Related Work

- [Transformer Grammars](https://arxiv.org/abs/2203.00633)
- [Language Models as Zero-Shot Planners](https://arxiv.org/abs/2201.07207)
- [ProTo: Program-Guided Transformer for Program Guided Task](https://arxiv.org/abs/2110.00804)

- [Incremental Regular Expressions](http://jkff.info/articles/ire/)
- [Tree Sitter](https://tree-sitter.github.io/tree-sitter/creating-parsers)

## Roadmap

- [x] Use a pretrained transformer to generate text (e.g. GPT-2)
- [x] Constrain generated text using exemplars
- [x] Constrain generated text using a simple program (e.g. regex)
- [ ] Test on different pre-trained models (e.g. FLAN-UL2, LLAMA, etc.)

## Program Implementations [TODO]

### Data

- **[Regex](./README.md)**: Extracts structured data from unstructured text using regular expressions.
- **[JSON](./README.md)**: Extracts JSON objects from unstructured text.
- **[JSON Schema](./README.md)**: Generates JSON objects that conform to a given JSON schema.
- **[XML](./README.md)**: Extracts XML objects from unstructured text.
- **[XML Schema](./README.md)**: Generates XML objects that conform to a given XML schema.

### Queries

- **[SQL Query](./README.md)**: Generates SQL queries that conform to a given SQL schema.
- **[GraphQL Query](./README.md)**: Generates GraphQL queries that conform to a given GraphQL schema.

### Code

- **[Python](./README.md)**: Generates Python code that conforms to a given Python grammar.
- **[Javascript](./README.md)**: Generates JavaScript code that conforms to a given JavaScript grammar.

### Other

- **[LangChain Prompt](./README.md)**: Generates text that conforms to a given LangChain agent.

### Custom

- **[Custom](./README.md)**: Generates text that conforms to an arbitrary program.