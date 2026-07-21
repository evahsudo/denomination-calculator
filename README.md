# Denomination Calculator

A simple, fast web app to calculate exact bank note denominations for Indian Rupee (INR) withdrawals. No more mental math at the bank counter.

**Live:** [denomination-calculator.pages.dev](https://denomination-calculator.pages.dev)

## The Problem

Every time you withdraw cash (especially in lakhs), the bank asks: "What denomination do you want?" You stand there doing mental math trying to figure out how many notes of ₹500, ₹200, ₹100 etc. you need. This tool solves that in seconds.

## Features

- Enter any amount (₹10K to ₹20L+) via input or slider
- Choose which denominations you want (₹10, ₹20, ₹50, ₹100, ₹200, ₹500)
- Set percentage split with auto-balancing sliders (always totals 100%)
- Smart remainder absorption — no leftover amount, exact coverage
- Copy results to clipboard — hand it to the bank teller
- Works offline — runs entirely on your device
- Mobile-friendly dark UI
- Zero dependencies, single HTML file

## How It Works

1. Enter the withdrawal amount
2. Toggle on the denominations you want
3. Adjust the percentage sliders (they auto-balance to 100%)
4. Hit Calculate
5. Get exact note count per denomination
6. Copy and show at bank

## Calculation Logic

1. **Percentage allocation** — splits your amount by the percentages you set
2. **Greedy remainder fill** — any leftover from rounding gets filled starting from the largest denomination
3. **Exact coverage** — if the amount isn't perfectly divisible by the smallest note, it rounds up by one note (clearly shown)

## Tech Stack

- Pure HTML/CSS/JS (no framework, no build step)
- Hosted on Cloudflare Pages
- Indian number formatting (₹2,00,000 style)

## Deploy Your Own

```bash
npx wrangler pages deploy . --project-name=denomination-calculator
```

Or just drag the folder to [Cloudflare Pages Direct Upload](https://dash.cloudflare.com/?to=/:account/pages).

## Testing

150 unit tests covering:
- Indian number formatting
- Amount parsing
- Calculation accuracy (exact coverage for all common bank amounts)
- Auto-balance slider logic (stress-tested with 20 random adjustments)
- Edge cases (₹1, ₹3, amounts not divisible by any note)

Open `tests/test.html` in a browser to run the test suite.

## License

MIT
