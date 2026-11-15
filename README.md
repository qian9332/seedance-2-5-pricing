# Seedance 2.5 Pricing Data

What does a Seedance 2.5 clip actually cost? It depends entirely on which door you walk through. This dataset compares 8 access routes for ByteDance's AI video model, normalized to dollars per clip, with every number sourced and dated.

## The formula (use it for any resolution and duration)

```
cost per clip = dollars-per-second × duration × number of generations
```

Retries count: if you discard 2 of 3 attempts, you paid for 3. Budget for iteration, not just the final clip.

## 10-second 720p clip, ranked (no reference video)

| Platform | Cost | Notes |
|---|---|---|
| OpenRouter (API) | $2.31 | $0.23112/sec provider rate |
| Kie.ai | $3.15 | 63 credits/sec × $0.005 |
| Higgsfield | $3.43 | 70 credits × $0.049 ($49 plan) |
| WaveSpeed | $3.60 (promo $3.24) | $0.36/sec list, 10% promo |
| Dreamina (ByteDance) | $4.23 (promo ~$0.07) | 370 credits at $18-plan value |
| Magnific | $4.40 | competitor-reported |
| OpenArt | $4.55 | competitor-reported |
| Runway | $7.20 | competitor-reported |

Full per-resolution dataset: [seedance-2-5-pricing.csv](seedance-2-5-pricing.csv) — one row per platform × resolution, with `checked_date` on every row.

## The trap this dataset exposes

Never compare credit counts across platforms. Dreamina's 37 credits/sec and Kie's 63 credits/sec look similar, but their credits are worth different amounts — Dreamina's promo-month credit is ~$0.000184 while Kie's is $0.005, a **27× difference in credit value** ($0.005 ÷ $0.000184 ≈ 27). Compare dollars per second, never credit counts.

Also included: reference-video discounts. Kie drops 480p 28→17, 720p 63→38, 1080p 158→95 credits/sec; WaveSpeed drops ~40% across the ladder. Image-to-video undercuts text-to-video significantly on both platforms.

## Data rules

1. Every number carries `source_url` and `checked_date`. Rows we couldn't verify at source are marked `competitor-reported`.
2. List price and promo price are separate columns — promos expire.
3. Token-billed platforms (Volcano Engine) are excluded until a tokens→seconds conversion is verifiable.

## Sources

- Dreamina: https://dreamina.capcut.com/
- OpenRouter: https://openrouter.ai/bytedance/seedance-2.5
- Kie.ai: https://kie.ai/blog/seedance-2-5-pricing
- Higgsfield: https://higgsfield.ai/ (cross-platform blog, Oct 2026)
- WaveSpeed: https://wavespeed.ai/

All checked November 15, 2026. This category reprices often — verify before buying.

## Full analysis

For worked cost examples (what 10 test clips cost per route) and free-tier traps (why 80 free credits can't run one clip), see **[Prismstead: Seedance 2.5 Specs, How to Use & Pricing](https://prismstead.com/seedance-2-5/)**.

## License

CC BY 4.0. Attribute to Prismstead (https://prismstead.com/) with a link.
