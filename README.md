# Structured Response Demo

This is a demo app for the blog post [Creating App Features Using AI Assistant Structured Output](https://www.anders.co/blog/creating-app-features-using-ai-assistant-structured-output/).

## Running the app

1. Clone this repo, run `npm install`
1. Go to [OpenAI](https://openai.com/), create an Assistant (see below).
1. Go to [Upstash](https://upstash.com/), and creat a Redis database.
1. Make a copy of the `.env.example` file and rename it to `.env`
1. Add the api keys, assistant Ids, etc listed in the `.env` file.
1. Run `npm run dev` to run the app locally

## Creating the assistant

These are configs I used for the Assistant. Feel free to use as is or modify as needed.

### System instructions

```text
Create a 3-question multiple choice trivia game. For each game, randomly select 3 common trivia game categories and create one question in each category. Do not repeat questions that have been asked in previous games. Ensure one correct answer per question and logical, plausible distractor choices.

Provide your response in JSON format using the following structure:

- `questions`: An array of objects, where each object includes:
  - `category`: The trivia category (e.g., "Music").
  - `question`: The trivia question.
  - `choices`: An array of answer choices.
  - `correctAnswer`: The correct answer.

```

### Response format

Select `json_object`
