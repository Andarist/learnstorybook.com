---
title: 'Introduction to testing UIs'
tocTitle: 'Introduction'
description: 'Latest production-ready techniques used by leading engineering teams'
commit: 'e3c72c0'
---

<div class="aside">This guide is made for <b>professional developers</b> learning how to test UI components. Intermediate experience in JavaScript and React is recommended. You should also know Storybook basics, such as writing a story and editing config files (<a href="/intro-to-storybook">Intro to Storybook</a> covers all the basics).
</div>

<br/>

Testing UIs is awkward. Users expect frequent releases packed with features. But every new feature introduces more UI and new states that you then have to test. Every testing tool promises “easy, not flaky, fast”, but has trade-offs in the fine print.

How do leading front-end teams keep up? What's their testing strategy, and what methods do they use? I researched ten teams from the Storybook community to learn what works — Twilio, Adobe, Peloton, Shopify and more.

This post highlights UI testing techniques used by scaled engineering teams. That way, you can create a pragmatic testing strategy that balances coverage, setup, and maintenance. Along the way, we'll point out pitfalls to avoid.

## What are we testing?

All major JavaScript frameworks are component-driven. That means UIs are built from the “bottom-up”, starting with atomic components and progressively composed into pages.

Remember, every piece of UI is now a component. Yup, that includes pages. The only difference between a page and a button is how they consume data.

Therefore, testing UI is now synonymous with testing components.

![Component hierarchy: atomic, compositions, Pages and Apps](/ui-testing-handbook/component-testing.gif)

When it comes to components, the distinction between different testing methods can be blurry. Instead of focusing on terminology, let’s consider what characteristics of UIs warrant testing.

1. **Visual:** does a component render correctly given a set of props or state?
2. **Composition:** do multiple components work together?
3. **Interaction:** are events handled as intended?
4. **Accessibility:** is the UI accessible?
5. **User flows:** do complex interactions across various components work?

## Where should you focus?

A comprehensive UI testing strategy balances effort and value. But there are so many ways to test that it can be overwhelming to figure out what’s right for any given situation. That’s why many teams evaluate different testing techniques using the criteria below.

- 💰 **Maintenance cost:** time and effort required to write and maintain the tests.
- ⏱️ **Iteration speed:** how fast is the feedback loop between making a change and seeing the result.
- 🖼 **Realistic environment:** where the tests are executed—in a real browser or a simulated environment like JSDOM.
- 🔍 **Isolate failures:** a test fails, how quickly can you identify the source of the failure.
- 🤒 **Test Flake:** false positives/negatives defeat the purpose of testing.

For example, end-to-end testing simulates “real” user flows but isn’t practical to apply everywhere. The key advantage of testing in a web browser is also a disadvantage. Tests take longer to run, and there are more points of failure (flake!).

Now that we’ve covered the UI characteristics to test and the criteria to evaluate each testing method, let’s see how teams design their test strategy.

## Your UI testing strategy

UI testing is integral to delivering high-quality experiences. It can be confusing to figure out a pragmatic testing strategy because an application’s surface area is expansive, and there are plenty of ways to test it.

You end up balancing trade-offs. Some tests are easy to maintain but offer false assurance. Others evaluate the system as a whole but are slow.

After interviewing ten teams to determine which UI testing methods actually worked, I compiled a shortlist of tools they recommend.

- 📚 [Storybook](http://storybook.js.org/) for isolating components from their context to simplify testing.
- ✅ [Chromatic](https://www.chromatic.com/) to catch visual bugs in atomic components and verify component composition/integration.
- 🐙 [Testing Library](https://testing-library.com/) to verify interactions and underlying logic.
- ♿️ [Axe](https://www.deque.com/axe/) to audit accessibility
- 🔄 [Cypress](https://www.cypress.io/) to verify user flows across multiple components
- 🚥 [GitHub Actions](https://github.com/features/actions) for continuous integration

The table below summarizes each UI testing method’s pros and cons and how often it’s used.

![How to evaluate different testing methods](/ui-testing-handbook/evaluate-different-testing-methods.png)

## Let's get testing

In upcoming chapters, we'll dig deeper into each layer of the test stack and get into the mechanics of how to implement this testing strategy. But, we’re going to need something to test. I’ll be using the Taskbox app as an example. It’s a task management app similar to Asana.

Grab the code here to follow along: https://github.com/chromaui/ui-testing-guide-code

Note, the implementation details aren’t important since we’re focusing more on how to test this UI. We use React here, but rest assured, these testing concepts extend to all component-based frameworks.

![How to evaluate different testing methods](/ui-testing-handbook/taskbox.png)
