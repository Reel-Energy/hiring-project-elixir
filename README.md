# Reel - Hiring project for Elixir

## Purpose

As the next step in the interview process for the Senior Software Engineer job at Reel, we will ask you to complete this project. We will use your solution to the project to get a better understanding of your technical abilities and how you approach a technical challenge. Your solution will also be the starting point for our subsequent technical interview. The project is intended to be a small representation of the kind of work we do at Reel.

## Problem description

We receive electricity consumption data in a json format from a third party source. This data is used on our platform to analyse consumption patterns and to help companies get a better understanding of the emissions related to their consumption. To map this data to our internal consumption data format, we need a parser. Your task is to write this parser, as specified in the next section.

We have set up this project and written a few helper functions so you can focus on developing the parser itself.

We expect the project to take 2-3 hours to complete. You are always more than welcome to reach out to us if something needs clarification.

## Your task

#### 1. Write the consumption data parser

The function `parse/1` is defined in the `Parser` module at 'lib/parser.ex'. A sample of json consumption data is read and passed to `parse/1` by the existing helper functions. The data contains hourly consumption readings from a single metering point for a 48 hour period. You can inspect the sample data at 'data/consumption_data.json'.

We want you to write the code to parse the sample data provided to this function. The `parse/1` function is just a starting point - you can add functions and/or modules as you wish.

The output of the `parse/1` function needs to contain the 48 consumption readings from the sample data in the following format:

```
[
  %{
    quantity: 0.1,
    metering_point_id: "927613927390263674",
    interval_start: "2021-12-31T23:00:00Z",
    interval_end: "2022-01-01T00:00:00Z"
  },
  %{
    quantity: 0.08,
    metering_point_id: "927613927390263674",
    interval_start: "2022-01-01T00:00:00Z",
    interval_end: "2022-01-01T01:00:00Z"
  }
  ...
   %{
    quantity: 0.06,
    metering_point_id: "927613927390263674",
    interval_start: "2022-01-02T22:00:00Z",
    interval_end: "2022-01-02T23:00:00Z"
  }
]
```

#### 2. Write tests to verify your solution

Write tests in 'test/parser_test.exs'. Write as many or as few tests as you see fit to make you feel comfortable in the correctness of your solution. However, we only expect you to test the parser itself.

#### 3. Explain your solution

Write a short (1200 characters max) explanation of how your solution works and why you chose that particular solution.

## Running the program during development

1. Make sure you have Elixir installed (see https://elixir-lang.org/install.html)
2. Compile the project
   - `$ mix compile`
3. Start an iex session (interactive Elixir shell)
   - `$ iex -S mix`
4. Call the `run/0` function from within the iex session
   - `iex> Parser.run()`
5. Run your tests
   - `$ mix test`

## Submitting your work

1. Clone this repository locally
2. Create and switch to a local branch for development
3. Develop your solution
4. Once you're done, create zip of the main folder an name it `<your_name>.zip`
5. Send the following to christian@reel.energy
   1. The zip file
   2. The description of your solution in pdf or md format

## How we evaluate

We focus on three main points in our evaluation:

1. The output of the `parse/1` function is correct. That is, the timestamps, quantity, and metering_point_id of each consumption reading matches the corresponding reading in the input data. Further, the format of the output is as described in the previous section.
2. How you solved the task. There are many ways to approach a task like this.
3. Your reasoning about choosing this solution.
