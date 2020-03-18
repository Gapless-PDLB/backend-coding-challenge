# Gapless backend coding challenge

Hello and thanks for taking the time to try this out.

The goal of this test is to assert (to some degree) your coding and architectural skills. You're given a simple problem so you can focus on showcasing your development techniques.

As this is a code review process, please avoid adding generated code to the project. This makes our jobs as reviewers more difficult, as we can't review code you didn't write.

_Note: While we love open source here at Gapless, please do not create a public repo with your test in! This challenge is only shared with people we're interviewing and for obvious reasons we'd like it to remain this way._

## The tasks 🏁

### SQL

You are given 4 tables in the tables folder (as CSV).
Write an SQL query to retrieve the following data in one result table:

YEAR - CW - USERS - VEHICLES - EVENTS - REVENUE (in Euro)

- CW = Week of the year
- Users = count of new **users**
- Vehicles = count new added **vehicles**
- Events = count of added **events**
- Revenue = calculated by sum of price column in **orders** table (it is in cents in the raw data)

Desired result example (random data):
| YEAR | CW | USERS | VEHICLES | EVENTS | REVENUE |
| ------- |:-------:| ------:| ----------:| -------:| --------:|
| 2019 | 34 | 5292 | 7392 | 12030 | 320.56 |

The data sets can be found in the _tables_ folder of this repo.

### Node.js (if possible Typescript) and Micro Services

#### Task 1

You are given three data sets. One is a list of **vehicles** data entries that users have created. It consists of stats like vehicle make, model, year etc.
The second one is a list of **recalls** that apply to certain vehicles. Write a node service/script that can regularly check if the recalls database has new data that apply to the cars in the vehicles list and store that information in another table called **events** (third one in the set).

_Note: The model names that the users have created do not have to exactly match the ones from the recalls. Usually a loose matching fits the goal of the task. e.g.: the user entered a Mercedes Benz E200. The recall is for Mercedes Benz E-Class. Same for BMW: 320d -> 3-Series. Try to find a solution for that issue._

#### Task 2

This task is about APIs.
Write a service that offers an API endpoint but also retrieves data from an external source itself. For testing purposes we don't offer a real API endpoint for you but instead a JSON file which should be used as an online data source:

```
http://static.gapless.app/backend-coding-challenge/vins.json
```

Your service should offer an API endpoint which gets a VIN (vehicle identification number like _2C3LA53G68H110255_) as a parameter and returns the data you get from the JSON file. But only the data set that matches the sent VIN. If nothing was found your API should act and respond accordingly.

## What will we be looking at

- Attention to detail and scalability
- Code reusability, readability and maintainability
- API security, data validation etc.
- Finding the right point of abstraction in your helpers functions and APIs

## Evaluation Criteria

- You're free to use as many third party JS libraries that you see fit
- Tests, type checking, linting... are nice to have

##### Happy hacking!
