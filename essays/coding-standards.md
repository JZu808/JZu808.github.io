---
layout: essay
type: essay
title: "I Hate Red Squiggly Lines"
# All dates must be YYYY-MM-DD format!
date: 2026-09-24
published: true
labels:
  - Software Engineering
  - Coding Standards
  - ESLint
---


## More than spaces and braces

When most people hear "coding standards," they think of small stuff like how many spaces to indent or where the curly brace goes. A coding standard is really a set of rules for how code should be written, including which language features to use and which to avoid. ESLint is the tool that checks my code against those rules. After using it in VS Code, I think a good standard does more than keep code tidy. It steers you away from common mistakes and teaches you the language along the way.

## What ESLint caught

One of my first JavaScript code blocks looked like this:

```javascript
var total = 0;
for (var i = 0; i < prices.length; i++) {
  if (prices[i] == '') continue;
  total = total + prices[i];
}
```

ESLint flagged almost every line. It wanted `const` or `let` instead of `var`, and `===` instead of `==`. After fixing things, I ended up with:

```javascript
const total = prices
  .filter((price) => price !== '')
  .reduce((sum, price) => sum + price, 0);
```

None of those warnings were about looks. Each one pointed to a spot where JavaScript works differently than I expected.

## Learning from the rules

When ESLint told me to use `===`, I looked up why and found out that `==` converts types before comparing, so `0 == ''` is actually `true`. When it told me to stop using `var`, I learned the difference between function scope and block scope. I wouldn't have looked either of these up on my own, because my code seemed to work fine.

That's why coding standards can help you learn a language. Each rule is basically a lesson from someone who already made that mistake.

## Painful or useful?

Both. It is painful to see all those red lines under your code even though it could be perfectly functional, but I believe it is necessary to feel the pain in order to learn and avoid those mistakes so that it no will no longer feel painful. 

## Conclusion

Coding standards aren't just about formatting. They make code easier for other people to read, they catch bugs early, and they teach you the language as you go. I started the week annoyed by ESLint and ended it grateful for it.

## Use of AI

I used claude.ai to create sample prompts on what to write about, check my grammar, and format code blocks.
