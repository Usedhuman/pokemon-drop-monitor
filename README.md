# Pokémon Drop Monitor

Personal price and availability tracker for a short watchlist of Pokémon TCG products at U.S. retailers.

It checks retailer product data through official APIs where available (Best Buy Products API, Walmart Affiliate API), watches for out-of-stock → in-stock transitions at or below retail price, and sends a push notification with a link to the retailer's product page.

Single user, low volume, first-party retailer inventory only. All purchases are completed manually on the retailer's website or app.

## What it does

- Polls a configurable watchlist of products through each retailer's official API, staying well under published rate limits
- Tracks availability state changes so you get one alert per event, not one per poll
- Filters out listings above your configured maximum price and third-party marketplace sellers
- Sends push notifications (Pushover, ntfy) containing the product page link
- Local status page showing last check, latency, and current state per product and retailer

## What it does not do

- No automated checkout or purchasing
- No browser automation
- No scraping of sites that prohibit automated access
- No circumvention of rate limits, CAPTCHAs, or bot protection

## Stack

Python 3.12, FastAPI, httpx, SQLite, APScheduler, Docker.

## Status

Early development. Starting with Best Buy, then Walmart.

## Configuration

Secrets live in a local `.env` file (see `.env.example`); nothing is committed. Watchlist and thresholds live in `config.yaml`.

## License

MIT

---

Impact-Site-Verification: 3067c63c-9324-4069-80d2-96346945cb55
