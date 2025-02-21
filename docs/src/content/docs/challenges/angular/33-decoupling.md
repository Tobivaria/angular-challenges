---
title: 🟠 Decoupling Components
description: Challenge 33 is about decoupling two strongly coupled components using Injection Token
sidebar:
  order: 106
---

:::note
WIP: The following documentation will be reviewed and improved. However, you can still take on the challenge. If you don't understand a certain part, please feel free to reach out or create an issue.
:::

<div class="chip">Challenge #33</div>

> Big thanks to **Robin Goetz** and his [Spartan Project](https://github.com/goetzrobin/spartan).
> This challenge was proposed by Robin and is strongly inspired by his project.

## Information

The goal of this challenge is to separate the behavior of a component from its style. For the purpose of this challenge, we will be working on a button element. When we click on it, we will toggle a _disabled_ property which will change the style of the element. This is quite useless in real life but the challenge aims to demonstate a useful concept.

The behavior of the component (referred to as the _brain_ in the Spartan stack) is located in the brain library. The styling part (referred to as the _helmet_) is located inside the helmet library. Both libraries cannot depend on each other because we want to be able to publish them separatly. To help us address the issue, we are using the Nx enforce eslint rule. You can find more details [here](https://nx.dev/core-features/enforce-module-boundaries);

However the button's helmet needs to access the state of the component to style the button differently based on its state. As mention above, we cannot import the `BtnDisabledDirective` directly into the helmet library as done currently. If you go to [`BtnHelmetDirective`](../../libs/decoupling/helmet/src/lib/btn-style.directive.ts), you will encounter a linting error. **A project tagged with "type:hlm" can only depend on libs tagged with "type:core"**.

## Statement

The goal of this challenge is to find a way to decouple both Directives.

### Hint

<details>
  <summary>Hint 1</summary>
  Carefully read the title of the challenge 😇
</details>

---

:::note
Start the project by running: `npx nx serve decoupling`.
:::

:::tip[Reminder]
Your PR title must start with <b>Answer:33</b>.
:::

<div class="article-footer">
  <a
    href="https://github.com/tomalaforge/angular-challenges/pulls?q=label%3A33+label%3Aanswer"
    alt="Decoupling Components community solutions">
    ❖ Community Answers
  </a>
  <a
    href='https://github.com/tomalaforge/angular-challenges/pulls?q=label%3A33+label%3A"answer+author"'
    alt="Decoupling Components solution author">
    ▶︎ Author Answer
  </a>
  </div>
