# Loan Tracker ₪

A single-file web app for tracking a personal loan with compound interest. No build step, no dependencies — just open `index.html` in any browser.

## Features

- **Dashboard** — overview cards, payment breakdown (principal vs. interest), payoff progress bar, and scenario comparison
- **Payment Log** — add, edit, and delete payments; each entry shows the principal/interest split and running balance
- **Settings** — configure original loan amount, annual interest rate, and start date
- **Scenario Comparison** — side-by-side view of "With interest" vs. "No interest" (balance + projected payoff)
- **Export / Import** — back up and restore all data as JSON
- **Persistent storage** — all data saved to `localStorage` automatically
- **Mobile-friendly** — responsive layout, sticky header, touch-friendly controls

## Interest Calculation

Monthly compound interest:

```
monthly_rate = (1 + annual_rate)^(1/12) − 1
```

Each calendar month, interest accrues on the current balance, then any payments made that month are applied — **interest first, then principal** — matching standard amortisation behaviour.

## Defaults

| Setting | Default |
|---------|---------|
| Original amount | ₪177,000 |
| Annual interest rate | 2% |
| Start date | 5 years before today |

## Usage

1. Open `index.html` in a browser (no server needed).
2. Go to **Settings** to enter your loan details and start date.
3. Go to **Payments** → **Add Payment** to log each payment with its date and amount.
4. The **Dashboard** updates automatically with current balance, payoff projection, and the interest vs. no-interest comparison.
5. Use **Export** (top-right or Settings tab) to save a JSON backup. Use **Import** to restore.

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Esc` | Close modal |
| `Ctrl+Enter` / `⌘+Enter` | Save payment (when modal is open) |

## File Structure

```
index.html   ← entire app (HTML + CSS + JS, self-contained)
README.md
```
