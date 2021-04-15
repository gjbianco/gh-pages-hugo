---
title: "How to Hire a JavaScript Developer"
date: 2021-04-15
draft: false
---

Over the years, I've been asked about what to look for when hiring a JavaScript developer.

Having focused the majority of my career on this ecosystem, I have seen various tools and techniques come and go.
Knowing jQuery used to be required.
Now, it's not even a recommendation.
Same with AngularJS, and Bower, and Grunt, etc.

The ecosystem has changed dramatically.
Necessarily so, in order to improve, but that does mean it can be hard for devs to keep up.

## Caveats

These are my (current) viewpoints on what to look for when trying to hire somebody for a JS-focused position.

This is by no means exhaustive and expect it to be out of date within a few years.

Additionally, separate the skills for UI and Node.js.
Both are of course JS, but require fundamentally different understandings.
e.g. most UI devs will know some Node and vice-versa, but most people will specialize more in one or the other.

Personally, I've done a lot more with UI, so keep that in mind.

## General Topics

Focus on their understanding of core JS ecosystem fundamentals.
Somebody familiar with the fundamentals will have much easier time learning framework specifics -- even ones that are fairly new to them.

I would say the single most important skill to have in that regard is handling asynchronous code paradigms in JS.
Again, that would be things around the promise spec (promises, async, await, etc.).
One example question I've used when interviewing people is asking them to compare usage and structural differences between callbacks and promises.

Another general question might be to ask their favorite feature/change introduced in ES2015 (this one is a little dated at this point, admittedly).

## TypeScript

Personally, I believe TypeScript _can_ provide a ton of value and sanity over writing plain JavaScript.

However, it is gaining popularity on resumes and by no means a silver bullet.
The compiler can offer a lot of really helpful checks, but it also provides no guarantees that your code is actually good.

Quite often, I see a lot of TypeScript code that is ultimately JavaScript but with extra steps.
The biggest sin here is the implicit (or especially _explicit_) use of `any`s.
A strong TS developer should be able to explain why this is such a big problem and provide general steps for avoiding it.

I am very biased here, but I expect a strong TS developer (that also has a strong JS background) to use the `class` keyword pretty minimally.
In most or all cases, it could likely be replaced with `interface`.
Traditional inheritance patterns (especially those from Java) do not fit well with JavaScript (even when using TypeScript), despite the keyword similarities.

These latter two are particularly true for React development, but less true for (modern) Angular.

## UI Focused Devs

If they list more than one UI framework, ask them to compare and contrast the structural differences and paradigms in each.
Pretty much all of them use components of some flavor, but what does component composition look like in each one?
How do "controllers" and "services" work in each (they may use different terms for them)?
How might you structure your client-side router in an SPA?
Input validation?

For a senior person, they should be very familiar with packaging and bundling.
e.g. how do their imports affect tree shaking?
Thoughts on CDN usage?

A senior person should also be familiar with testing tools.
Largely unit testing frameworks (e.g. mocha+chai, jest) and functional testing frameworks (e.g. Selenium, Cypress, Puppeteer/Playwright).

Bonus points if they are familiar with deploying a UI within a microservices architecture and building APIs.

## Backend and Node.js Focused Devs

I will keep this section pretty brief as general questions for writing web services apply.
e.g. questions about database queries.

Look to see how they organize model/entity code with API layer code.

Can they explain what an Express "middleware" is and give a simple example of a custom one you might write?
