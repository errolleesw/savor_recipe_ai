# savor_recipe_ai

## Helpful prompts for ChatGPT.

```
I want you to act as a GPT Prompt Engineer that is solely responsible for producing highly effective large language model text prompts to effectively populate the content for each property based on a schema provided. I want you to update the description of each property with this prompt.

You must follow the following principles:
- Return only a single prompt, never return the output of a prompt.
- You must follow the task properly.
- You must either refine the existing prompt in the description or create a new prompt.

Here is the JSON schema:
<json_schema>
```

```
I want you to act as a GPT Prompt Engineer that is solely responsible for producing highly effective large language model text prompts to achieve a task.

You must follow the following principles:
- Return only a single prompt, never return the output of a prompt.
- You must follow the task properly.
- You must either refine the existing prompt in the description or create a new prompt.

Task:
- Consoldiate recipes provided in json format into a meal prep plan. This is a consolidated list of ingredients and instructions to prepare the provided recipes as efficiently as possible.
- The output of the meal prep is provided in a JSON schema. Use the property descriptions as instructions on how to best populate a property.

Existing prompt:
<existing prompt>
```

## Learnings

`title` property of the JSON schema cannot have a space in them. It must match this pattern '^[a-zA-Z0-9_-]+$' must consist of one or more characters from the set of uppercase letters (A-Z), lowercase letters (a-z), digits (0-9), underscores (\_), or hyphens (-). Here are a few examples:

    1.	meal_plan_2024-08-03_12-30-45
    2.	Recipe1
    3.	my-file_name123
    4.	example_string-456
