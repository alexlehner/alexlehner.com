---
layout: post
title: "On CSS Specificity"
category: articles
tags: [code, career]
modified: 2022-03-30
---

It might surprise you that a sizeable portion of the Mailchimp product has a basic CSS architecture. Philisophically it's not far from [Tailwind](https://tailwindui.com/) — Reusability focused utility classes drive component creation. Semi-officially the approach was known as Object Oriented CSS accompanied with [Less](https://lesscss.org/) as a preprocessor and [BEM](http://getbem.com/) for naming. Yeah, the approach is long in the tooth, but [hey it's profitable](https://techcrunch.com/2021/09/13/intuit-confirms-12b-deal-to-buy-mailchimp/ "Mailchimp is sold to Intuit for 12 billion dollars").

```css
#palette {
  img.color-combo-image {
    max-width: 50%;
    margin-bottom: @lv6;
  }
}
```

Let's chat about this snippet. If we're trying to make a round color swatch, it totally works. But we can make it better without introducing leaky styles.

It's good to keep in mind that our CSS (like most websites) is global. This means changing one style could have unpredictable impact across different pages. It's easy to assume that we'd WANT to use specificity to safeguard/protect our styles. What I've learned in practice though is that the exact opposite is true.

**The flatter our CSS specificity tree is, the easier it is to maintain.**

The Cascade is CSS's biggest strength and weakness. Unchecked and at-scale it can create a mess of context-specific spaghetti code. As we're writing new CSS, we should also consider how easy it would be to delete. Because of the global nature, safely removing CSS is tough. Knowing every consumer of the CSS is in a 10+ y/o app is fairly difficult. For very specific class name, it's easy to `grep`. For HTML elements, IDs, and other non-specific blocks of text, find-ability goes down fast.

## Case study

CSS preprocessors make it easy to accidentally introduce specificity. Taking a look at this snippet, this will end up compiling down to the following CSS declaration:

```css
#palette img.color-combo-image {
  max-width: 50%;
  margin-bottom: 36px;
}
```

That creates a specificity score of 111 which is pretty high. [https://specificity.keegan.st/](https://specificity.keegan.st/) is a handy resource for measuring specificity. Ideally we'd aim for scores of 001 or 010.

It's usually safe to assume that someone will need to use or reuse your style. As it's written, they wouldn't be able to use this style unless it's an `<img>` tag beneath an HTML element with the id of `palette` and the node(s) has a class of `color-combo-image`

Folks may also need to override some aspect of style rule. Overriding this downstream we would have to create a specificity score of at least 121 or 112.

To make a _more_ specific rule, we'll have to jump on a specificity treadmill. It's a treadmill that's tough to get off.

### Specificity Treadmill

_Marked in ascending order of specificity_

```css
/* 112 */
#palette div img.color-combo-image {
}

/*/* 121 — Very specific */
#palette .something img.color-combo-image {
}

/* 121 — Note the appending of another class doesn't change
 underlying specificity as compared to prefixed nesting. */
#palette img.color-combo-image.anotherClass {
}

/* 211 — Highlyyyy specific */
#newContext #palette img.color-combo-image {
}

/* Nuclear option — Super undesirable.
Same declaration with `!important`*/
#palette img.color-combo-image {
  // Might as well join the dark side
  max-width: 50% !important;
  margin-bottom: 36px !important;
}
```

### What now?

As you're writing CSS, try to consider some of the following:

- How much specificity do I really need?
- What is the lowest specificity I can use to get the job done?
- Should I really be styling by an HTML Element?
- Could BEM help to improve readability and lower specificity?
- Is this a component? A utility class? A one-off? Maybe the prefix should indicate that.

### Alternative

What if this was written this way?

```css
/* 010 specificity score. */
.c-colorComboPreview {
  max-width: 50%;
  margin-bottom: (@base-unit * 6);
}
```

Writing it this way achieves the following:

- Overrides can use BEM and the modifier syntax `--modifierName`
- If we need to make a more specific rule, that's doable with clear context.
- It's easily `grep`-able
- It's flexible enough to be used on images and other node types
- It can be used regardless of parent nodes (doesn't need to be under #palette)
- The `c-` indicates that it is a "component" — a thing that operates independently of other styles.
- It can be used in conjunction with utility classes without fighting margin specificity.
- It uses camel case which is the preferred class name format.
- Deleting of this code should be easy.

---

## TL;DR

When you start with a high specificity, the only path towards overriding is more specificity. Start low and only add when explicitly necessary.
