# Concepts of Functional Programming in Javascript

After a long time learning and working with object-oriented programming, I took a step back to think about system complexity.

Doing some research, I found functional programming concepts like immutability and pure function. Those concepts are big advantages to build side-effect-free functions, so it is easier to maintain systems — with some other benefits.
In this post, I will tell you more about functional programming, and some important concepts, with a lot of code examples. In Javascript!

## What is functional programming?

Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data 

## Pure functions

The first fundamental concept we learn when we want to understand functional programming is pure functions. But what does that really mean? What makes a function pure?

### It returns the same result if given the same arguments

Imagine we want to implement a function that calculates the area of a circle. An impure function would receive radius as the parameter, and then calculate `radius * radius * PI:`

See that our pure function increaseCounter returns 2, but the counter value is still the same. The function returns the incremented value without altering the value of the variable.
If we follow these two simple rules, it gets easier to understand our programs. Now every function is isolated and unable to impact other parts of our system.
Pure functions are stable, consistent, and predictable. Given the same parameters, pure functions will always return the same result. We don’t need to think of situations when the same parameter has different results — because it will never happen.

#  Refactoring JavaScript for Performance and Readability (with Examples!

Recently, I wrote an article about how to write very fast JavaScript. Some of the examples took it to the extreme and became very quick at the cost of being totally unmaintainable. There's a middle ground between speed and comprehension and that's where good code lives.

We're going to refactor some pieces of code based off real examples that I've come across. Sometimes I'll need to perform this kind of refactoring on my own code before submitting a PR. Other times I'll do a small refactor of existing code at the start of a story or bug to make my changes easier to implement.

## Scenario 1

We're an URL-shortening website, like TinyURL. We accept a long URL and return a short URL that forwards visitors to the long URL. We have two functions.

Problem: what happens if getLong is called with a short URL that isn't in the store? Nothing is explicitly returned so undefined will be returned. Since we're not sure how we're going to handle that, let's be explicit and throw an error so that problems can be spotted during development.

Performance-wise, be careful if you're iterating through a flat array very often, especially if it's a core piece of your program. The refactor here is to change the data-structure of URLstore.

Currently, each URL object is stored in an array. We'll visualize this as a row of buckets. When we want to convert short to long, on average we need to check half of those buckets before we find the correct short URL. What if we have thousands of buckets, and we perform this hundreds of times a second?

## Scenario 2

We're a social media website where user URLs are generated randomly. Instead of random gibberish, we're going to use the friendly-words package that the Glitch team works on. They use this to generate the random names for your recently created projects!

It's often said that a function should do one thing. Here, createUser does one thing .. kinda. It creates a user. However, if we're thinking ahead to the future, there's a good chance (if our business is successful) that this function is going to grow very large indeed. So let's start early by breaking it up.

You may have also noticed that there is some duplicated logic in our random functions. The friendly-worlds package also offers lists for 'teams' and 'collections'. We can't go around writing functions for every option. Let's write one function that accepts a list of friendly things.

const friendlyWords = require('friendly-words');

const generateURL = user => {
  const pick = arr => arr[Math.floor(Math.random() * arr.length)];
  user.url = `${pick(friendlyWords.predicates)}-${pick(friendlyWords.objects)}` +
    `-${pick(friendlyWords.objects)}`; // This line would've been too long for linters!
};

`async function createUser(email) {`
 ` const user = { email: email };`
 ` // The URL-creation algorithm isn't important to this function so let's abstract it away`
 ` generateURL(user);`
 ` await db.insert(user, 'Users')`
`  sendWelcomeEmail(user);`
`}`