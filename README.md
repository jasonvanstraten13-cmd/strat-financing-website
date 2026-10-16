# Strat Finances website

The marketing site for Strat Finances, accounting for South African small businesses.

It is a single static page: `index.html` plus the images in `assets/`. There is no build step and no JavaScript framework; fonts load from Google Fonts.

## Preview locally

Open `index.html` in a browser, or serve the folder:

```
npx serve .
```

## Deploy

Any static host works. On Vercel: import this repository, leave the framework preset as **Other**, and deploy. No build command or output directory is needed.

## Before going live

- **Button links.** "Start free trial" and "Sign in" are set in one place, the `LINKS` line at the top of the script near the end of `index.html`. Point them at the app's sign-up and sign-in pages.
- **Pricing.** The plans (Solo R149, Business R299 a month; yearly is two months free) are in the `#pricing` section. Each price has `data-monthly` and `data-annual` values that the Monthly/Yearly switch swaps between.
- **Promises.** The page says the accountant signs in free and offers a free trial. Change the copy if either isn't your policy.

## Design notes

Motion and interaction follow [Emil Kowalski's design engineering skills](https://github.com/emilkowalski/skills):

- Custom curves only (`--ease-out`, `--ease-in-out` in `:root`); never `ease-in`.
- Only `transform`, `opacity` and `clip-path` animate. UI transitions stay under 300ms; the hero reconciliation demo is explanatory, so it runs longer.
- Every button scales to 0.97 on press. Hover styles apply only on devices with a real pointer.
- The hero demo and pricing switch use transitions, so they can be interrupted and replayed cleanly.
- Product windows reveal once on scroll, and only if they start below the fold, so the page is complete without scrolling.
- `prefers-reduced-motion` gets fades instead of movement; `prefers-reduced-transparency` gets a solid nav bar.
- Light and dark themes follow the visitor's system setting.
