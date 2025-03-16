
**`sanitize.css` does not just remove styles; it also adds opinionated styles** to improve consistency, security, and accessibility.

```

The creator of Sanitize.css preferred 19 opinionated styles to be the default styles, believing they provide a better foundation for web development."
```

1. It **removes many default browser styles**, like button backgrounds, list bullets, and form element appearances.
2. It **adds new opinionated styles**—such as better typography, a standardized box-sizing model, and security fixes.

For example:

- It removes default button styles (`background`, `border`, etc.), but it also ensures that **buttons inherit font settings** from their parent.
- It removes list styles (bullets, numbers) but **doesn’t completely erase their structure**, allowing developers to redefine them easily.

So, unlike a **pure reset** that just removes styles (`reset.css`), `sanitize.css` also **modifies and replaces some defaults** to create a **better foundation** for styling.

