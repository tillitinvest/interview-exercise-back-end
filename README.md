# TILLIT back-end interview exercise

Hi! We know not everyone does well in live coding exercises, but we still want to get a picture of how you as a developer approach solving problems with code.

So, we've devised this quick scenario for you to show us your skills with. Please read this in full, especially the section at the end that covers our assessment criteria and what we _aren't_ expecting, so you don't burn time on things we're not focusing on.

As a guide, we think this exercise can be completed adequately in under two hours - though it's not a race.

# The exercise

We're going to build a simple 'bank holidays' service, using some open data.

## Data source

You should use [the JSON data file available at gov.uk](https://www.gov.uk/bank-holidays.json). A copy of the file has been captured in this repository as a backup, in case the service goes down when you're trying to tackle the exercise.

## Requirements

For various reasons, we sometimes want to know whether a bank holiday lands on a particular day, or within some range of dates. Typically a bank holiday is one where financial instruments like funds and stocks aren't traded, and where we cannot expect to get up to date price information either.

> An aside: in reality the holidays that are interesting in finance may well be global in nature, depending on where you're trading - here we're going to assume we're just interested in the UK, and in particular that we're adhering to bank holidays in England and Wales.

In the file linked above, three divisions of the UK have their bank holidays listed. You'll need to parse the file and filter out only the relevant holidays to succeed.

### API functions

We would like you to build a REST API that fulfils the following requirements:

As an anonymous upstream API caller:

- I want to know if a given single date is an English bank holiday or not
- I want to know the number of market-open days between two inclusive dates
  - Here we mean 'Any day Monday to Friday that isn't also a English bank holiday'
- I want to know the dates of each English bank holiday falling between two inclusive dates

It should take less than an hour for a change to bank holidays being published on the Gov.UK site being taken into account by the API.

## Required tech

The solution should be written in C# against .NET Core, ideally - though beyond that you can make whatever choices you want.

And we'd recommend that if you're storing holiday data that you store it in-memory in whatever data structures you think best to service the requirements above, given the time constraints available. Don't worry about a database or distributed caching.

## What we'd like to see:

- Thought going in to how you're representing data through the API - date formats, request and response payloads and the actual API routes themselves
- Consideration of error conditions, and especially of input validation
- Use of appropriate data types and techniques to service the three different requests
- A separation of concerns between the API and any business logic you devise to fulfil the requirements
- Some tests (not looking for 100% coverage), with some interesting test cases considered

## What to do if you're running out of time

We'd rather see one of the requirements tackled really well than three of them done badly - so prioritise turning in a working solution to at least some part of the problem, and document what remains to be done if you find yourself up against time.

## What we _aren't_ expecting

We don't expect you to:

- Dockerise the solution or otherwise consider how it might be packaged for deployment
- Have integration tests or anything beyond unit testing (though we might ask about this in the interview)
- Use any distributed cache or similar for any storage requirements - in-memory statically-allocated data structures are perfectly adequate for now
- Necessarily use Swagger or anything else - though some notes on how to run and test the API would be helpful if you're not adding Swagger to the solution

## What to submit

- The solution files
- Any notes on how to run and test the project
- Any notes on what's left to do, or assumptions you made along the way

## Before you get started

A few notes before you get into things:

### This shouldn't take days

We don't expect this exercise to take more than a couple of hours to complete. If you're getting near that point, we'd recommend you stop and jot some notes down on what's left to do and what you'd do next.

### This isn't a trick question or an l33tcode test

We're interested in how you'd solve this in real life, as a practical programmer implementing a solution at work. Raw efficiency isn't the aim of the game (though radically inefficient solutions will be questioned), and we'd sooner see clear and correct code than anything double-clever.

### You define when you're done

The exercise is 'complete' when you say it is - we need enough information to make an assessment of your ability, but we're not expecting a production-grade application on the back of a two-hour unpaid assignment.

# Our assessment criteria

Roughly, we'll be looking to answer the following questions about you and your submission:

- Are you fluent with C#, and common .NET data structures and APIs?
- Is your code clear, concise and readable?
- Can you interpet requirements and make reasonable assumptions where needed?
- Is your code _correct_, with respect to the requirements and your assumptions?
- Did you handle edge-cases and scenarios not explicitly made in the requirements in a sensible way?
- Do you know how to write good unit tests? And can you prioritise _what_ needs tested?
- Do you understand the implications of your design choices? Can you explain them in a live code review?
