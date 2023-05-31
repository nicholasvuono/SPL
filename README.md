# SPL 🪄 - Structured Prompting Language (pronounced - spell)

## Syntax Example
```
import openapi

openapi.options = [
  model: 'text-davinci-003'
  max_tokens: 2048
  tempurature: 0.5
  top_p: 1
  n: 1
  stream: false
  logprobs: null
  //stop: null
]

openapi.prompt = [
  instructions: 'Answer the question based on the context below. Keep the answer short and concise. Respond "Unsure about answer" if not sure about the answer.'
  context: 'Teplizumab traces its roots to a New Jersey drug company called Ortho Pharmaceutical. There, scientists generated an early version of the antibody, dubbed OKT3. Originally sourced from mice, the molecule was able to bind to the surface of T cells and limit their cell-killing potential. In 1986, it was approved to help prevent organ rejection after kidney transplants, making it the first therapeutic antibody allowed for human use.'
  input: 'What was OKT3 originally sourced from?'
  outputIndicator: 'Answer:'
]

response = openapi.completions()

print(response.text) // 'Mice.'

```

## Output Example

```
import openapi

openapi.options = [
  model: 'text-davinci-003'
  max_tokens: 7
  tempurature: 0
  top_p: 1
  n: 1
  stream: false
  logprobs: null
  stop: '\n'
]

openapi.prompt = [
  instructions: null
  context: null
  input: 'Say this is a test'
  outputIndicator: null
]

response = openapi.completions()

print(response.text) // '\n\nThis is indeed a test'

// Response Object:
//
//{
//  "id": "cmpl-uqkvlQyYK7bGYrRHQ0eXlWi7",
//  "object": "text_completion",
//  "created": 1589478378,
//  "model": "text-davinci-003",
//  "choices": [
//    {
//      "text": "\n\nThis is indeed a test",
//      "index": 0,
//      "logprobs": null,
//      "finish_reason": "length"
//    }
//  ],
//  "usage": {
//    "prompt_tokens": 5,
//    "completion_tokens": 7,
//    "total_tokens": 12
//  }
//}

```
