# Senior Rails test

In this test you will code from scratch an imaginary feature for a coliving management system.

The questions may seem a bit vague. That's on purpose. We would like to see what you can come up with without too much guidance, and there is no single right answer. If you have doubts about what is asked exactly, make a decision and carry on. Don't hesitate to add comments to explain your thought process and choices.

Your code should work (obviously), but you're also expected to pay attention to code quality and design patterns, as if you were part of a team building a production app.

From one question to the next, you may have to modify code you wrote before. Don't plan ahead, instead try to find the best solution for each question independently, and package each question's code into a single commit.

Use whatever test framework you like. Only write tests when asked!

No need to deploy anything, your app should just run locally.

In case you run out of time or you're stuck, write some pseudo-code or a comment about what you think could be done.

When you're done, push your code to a GitHub repo and ping us!

## Setup

Start a Rails app in API config, with whatever db you want.

Set up a Studio model with a name attribute.

Set up a Stay model that belongs to a Studio, with a start date attribute and an optional end date attribute.

Set up seeds to populate the db with 2 studios, and three stays for each. Stays within a studio shouldn't overlap (no need to validate that), and one should have no end date.

## Spec

A fictional SPA posts a request with "holes", e.g. the person in studio 1 is absent between date A and date B and the person in studio 2 is absent from date C, forever.

- we must update the stays in the db taking into account the holes,
- then we must respond with a JSON description of the resulting holes.

As an example:

```
Stays for a given studio: ---[-----]---[------
Holes sent by SPA:        ------[----]---[-]--
Updated stays:            ---[--]------[-]-[--
Response:                 ---]--[------]-[-]--
```
