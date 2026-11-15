# Seedance 2.5 Pricing Data

What does a Seedance 2.5 clip actually cost? It depends entirely on which door you walk through. This dataset compares 9 access routes for ByteDance's AI video model, normalized to dollars per clip, with every number sourced and dated.

## The formula (use it for any resolution and duration)

```
cost per clip = dollars-per-second × duration × number of generations
```

Retries count: if you discard 2 of 3 attempts, you paid for 3. Budget for iteration, not just the final clip.

## 10-second 720p clip, ranked by LIST price (no reference video)

| Platform | Cost | Notes |
|---|---|---|
| Volcano Engine (official API) | ~$2.10 (est.) | ¥70/M tokens; formula-based estimate, billed by API usage; requires account + real-name |
| OpenRouter (API) | $2.31 | $0.23112/sec provider rate |
| Kie.ai | $3.15 | 63 credits/sec × $0.005 |
| Higgsfield | $3.43 | 70 credits × $0.049 ($49 monthly plan / 1,000 credits) |
| Dreamina (ByteDance) | $3.52 (promo ~$0.07) | 370 credits × $0.009524 ($15 renewal / 1,575 credits, confirmed at official page); assumes credits used within the month |
| WaveSpeed | $3.60 (promo $3.24) | $0.36/sec list, 10% promo |
| Magnific | $4.40 | competitor-reported |
| OpenArt | $4.55 | competitor-reported |
| Runway | $7.20 | competitor-reported |

Ranking basis: list prices. Dreamina's promo month is the cheapest consumer entry; Volcano's flash tier (~$1.40) is the cheapest API route. Full per-resolution dataset: [seedance-2-5-pricing.csv](seedance-2-5-pricing.csv) — one row per platform × resolution, with `checked_date` on every row.

## The trap this dataset exposes

Never compare credit counts across platforms. Dreamina's 37 credits/sec and Kie's 63 credits/sec look similar, but their credits are worth different amounts — Dreamina's promo-month credit is ~$0.000184 while Kie's is $0.005, a **27× difference in credit value** ($0.005 ÷ $0.000184 ≈ 27). Compare dollars per second, never credit counts.

Also included: reference-video discounts. Kie drops 480p 28→17, 720p 63→38, 1080p 158→95 credits/sec; WaveSpeed drops ~40% across the ladder. Image-to-video undercuts text-to-video significantly on both platforms.

## Data rules

1. Every number carries `source_url` and `checked_date`. Rows we couldn't verify at source are marked `competitor-reported`.
2. List price and promo price are separate columns — promos expire.
3. Volcano Engine is token-billed: figures are estimates from the official token formula ((input+output duration) × width × height × fps ÷ 1024, ¥70/M tokens for 720p). Actual billing is by API-returned usage.
4. Dreamina's renewal price is **confirmed $15/month** for 1,575 credits per the official pricing page (dreamina.capcut.com/seedance/seedance-2-5-pricing-2026). The $3.52 figure assumes the 1,575 credits are used within the month — unused credits raise the effective per-credit price.
5. Higgsfield figures use the $49 monthly plan; their own comparison page shows lower per-second rates under the MAX annual plan with credit discounts — different plan, not an error.

## Sources

- Volcano Engine (official): https://www.volcengine.com/docs/82379/1520757
- Dreamina (official): https://dreamina.capcut.com/seedance/seedance-2-5-pricing-2026
- OpenRouter: https://openrouter.ai/bytedance/seedance-2.5
- Kie.ai: https://kie.ai/blog/seedance-2-5-pricing
- Higgsfield: https://higgsfield.ai/ (cross-platform blog, Oct 2026)
- WaveSpeed: https://wavespeed.ai/

All checked November 15, 2026. This category reprices often — verify before buying.

## Full analysis

For worked cost examples (what 10 test clips cost per route) and free-tier traps (why 80 free credits can't run one clip), see **[Prismstead: Seedance 2.5 Specs, How to Use & Pricing](https://prismstead.com/seedance-2-5/)**.

## License

CC BY 4.0. Attribute to Prismstead (https://prismstead.com/) with a link.
