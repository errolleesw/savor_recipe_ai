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

## Hyper Recipe Thoughts
Why are recipes still so flat. Still just a replica of printed recipes? Why can't they be more interactive and better formatted to help you cook more efficiently.

Structured schemas for recipes already exist:
- [Recipe Schema Markup (Structured Data) Json-ld generator | Honey & Jam](https://honeynjam.com/tools/schema-markup-generators/recipe)
- [Recipe - Schema.org Type](https://schema.org/Recipe)
- [Recipe Schema Markup | Google Search Central  |  Documentation  |  Google for Developers](https://developers.google.com/search/docs/appearance/structured-data/recipe)

But they're missing a few things.

Things that can be improved.
- Ingredients are stored as text in an array, which means, they can't have their own properties. We should be able to split up ingredients into quantity, unit and item. We should also be group up similar ingredients by category.
- Ingredients shoudl be standardised against the raw item that is available, either in the pantry or fridge, but more typically, what can be purchased at the local grocery store.
  - There should be no "processing" / "preparation" steps in the ingreidents. E.g. it shouldn't say roughly chopped parsely, it should just say Parsely, the chopping should be included in the steps.
- Nice to have: It should also easily suggest alternatives if the item is not available.
- There should be standardised short-hands for quantity measurements.
  
- Recipe steps should include the preparation of the ingredients and be organised as efficiently as possible, e.g. if an item needs to go in the oven or simmer for a while, prep that first and prep other items while that is cooking.
- Steps should include quantities of the ingredients.
- Steps should visiually indicate the difference between ingredients, duration, equipment.

Some ideas:
- Use [HowToItem - Schema.org Type](https://schema.org/HowToItem) schema as a baseline for ingredients.
- Use [HowToTool - Schema.org Type](https://schema.org/HowToTool) schema as a baseline for equipment.
- Use [HowToSection - Schema.org Type](https://schema.org/HowToSection) schema to group ingredients and equipment.

### Recipe Metadata
- Name
- prepTime
- tags
- 

### Ingredients
  
