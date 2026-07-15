## Learning Outcomes

- Students will translate unstructured plain text into semantic HTML, choosing elements based on the *meaning* of the content rather than its appearance.
- Students will author a stylesheet from scratch, applying the cascade, inheritance, selectors, combinators, and CSS custom properties to style that markup.
- Students will practice the discipline of separating structure (HTML) from presentation (CSS) under real time pressure.

This is an abbreviated homework - we want you to be have a general understanding of CSS as you head into the midterm, we'll be doing more applied work afterwards. 

Remember to build exactly what is asked - nothing more!

## Setup

- You are given exactly one file: `cheese.txt`. It is plain, unstructured text — no tags, no classes, no hints.
- You will produce two files: `cheese.html` and `cheese.css`. Boilerplate (`<!doctype>`, `<html>`, `<head>`, `<meta>` tags, `<title>`) is expected but not separately graded — we're assuming you have that down!
- Do not add content that isn't in `cheese.txt`. Do not remove any of it. Your job is structure and style, not rewriting.
- All CSS must be hand-authored. No frameworks (Bootstrap, Tailwind, etc.).

## Part 1 - HTML Structure (20 pts)

Read `cheese.txt` closely — its headings, its list-like sections, its quotation, its warning, its little survey at the end are all *signals* about where each of these belongs. 

Your `cheese.html` must use the following:

| Tag / Attribute                                              | Pts  |
| ------------------------------------------------------------ | ---- |
| `<header>`, `<main>`, `<footer>`                             | 3    |
| `<h1>`, `<h2>`                                               | 2    |
| `<time datetime="">`                                         | 1    |
| `<article>`, `<section>`                                     | 2    |
| `<q>`                                                        | 1    |
| `lang` attribute                                             | 2    |
| `class` attribute (on the two Latin terms)                   | 1    |
| `<dl>`, `<dt>`, `<dd>`                                       | 3    |
| `<blockquote>`, `<footer>` (inside it, for attribution)      | 2    |
| `id` attribute (on the warning paragraph)                    | 1    |
| `<form>`, `<fieldset>`, `<legend>`, `<label>`, `<input>`, `<button>` | 2    |

Two placement rules to keep in mind as you structure things, since Part 2's CSS depends on them:

- The byline ("by The CSE Cheese Society...") must live inside your `<header>`.
- The opening paragraph of your `<article>` must be a **direct child** of `<article>` — don't nest it inside a `<section>` along with the rest of that first topic's text.

## Part 2 - CSS Styling (27 pts)

**Include a link to your repo at the top of `cheese.css` as a comment.**

It's time to style the HTML you just wrote!

You are not trying to match anyone else's exact colors or fonts,  you are demonstrating that you can wield each of the following correctly. Property choice is otherwise up to you!

| Requirement                  | Details                                                      | Pts  |
| ---------------------------- | ------------------------------------------------------------ | ---- |
| Custom properties            | Define at least 4 CSS variables on `:root` (e.g. two colors, a font stack, a layout value) and consume each via `var()` in at least two different rules | 3    |
| Global reset                 | A rule using the universal selector `*` that zeroes out `margin` and sets `box-sizing: border-box` | 2    |
| Inherited typography         | Set `font-family`, `color`, and `line-height` once on `body` and let them inherit — don't repeat them on every element | 2    |
| Unit tour                    | Use `rem` for at least one font size, `em` for at least one value that should scale with its *local* context (e.g. padding inside a blockquote), and `%` or a viewport unit for at least one layout value. Each in a context where that unit is the right choice, not interchangeable | 4    |
| Attribute selectors          | One rule using `[lang]` and one rule using `[type="text"]`   | 2    |
| Class selector               | Style your Latin-term class from Part 1                      | 1    |
| ID selector                  | A rule that specifically targets the `id` you set on the warning paragraph in Part 1 | 1    |
| Descendant combinator        | A rule that only targets `<p>` elements *inside* `<header>`  | 1    |
| Child combinator             | A rule that only targets `<p>` elements that are *direct children* of `<article>` | 1    |
| Adjacent sibling combinator  | A rule that targets a `<dd>` immediately following a `<dt>`  | 1    |
| State pseudo-classes         | `:hover` on your links, `:focus` on your interactive elements (inputs, buttons, links — do not remove focus outlines without replacing them), and `:checked` combined with `+` to style a `<label>` when its checkbox is checked | 3    |
| Generated content            | One `::before` (or `::after`) rule that uses `content:` to insert something not present in the HTML | 2    |
| Cascade in action            | Somewhere in your HTML, add a page-scoped `<style>` block that overrides one of your own `cheese.css` rules at equal specificity, and add a comment explaining *why* the override wins | 2    |
| File inclusion via `@import` | Split your custom properties (`:root` variables) into a second CSS file and pull it into `cheese.css` with `@import`. Add a comment noting that `<link>` is still preferred in production and why | 2    |

## Restrictions

- Hand-authored CSS only — no frameworks, no copy-pasted starter templates.
- Stick to the property budget: you shouldn't need much beyond `color`, `background`, `font-family`, `font-size`, `font-weight`, `font-style`, `line-height`, `margin`, `padding`, `border`, `max-width`, `text-align`, `text-decoration`, `content`, and `box-sizing`. If you find yourself reaching for a lot more than that, you're probably over-engineering a lab you have a day and a half for.
- You should still not be using JS in your assignment at this stage.

## Final Submission

Two things:

1. Link to your `cheese.html` / `cheese.css` in a repo which you will submit the link to in Gradescope.
2. Link to the deployed page.
