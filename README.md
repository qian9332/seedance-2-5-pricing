# Seedance 2.5 Pricing Data

What does a Seedance 2.5 clip actually cost? It depends entirely on which door you walk through. This dataset compares the four main access routes for ByteDance's AI video model, with every number sourced from the platform's own pricing page.

## The data

| Platform | Pricing model | 10s 720p clip | Value per credit |
|---|---|---|---|
| Dreamina (ByteDance) | Subscription promo: $0.29 first month w/ 1,575 credits, renews $15/mo | ~$0.07 (promo effective) | ~$0.000184 |
| OpenRouter (API) | $0.23112/sec provider rate | ~$2.31 | n/a (billed per second) |
| Kie.ai (reseller, beta) | 480p 28 / 720p 63 / 1080p 158 credits/sec; 1 credit = $0.005 | ~$3.15 | $0.005 |
| Higgsfield (reseller) | 370 credits ≈ $4.23 per clip | ~$4.23 | varies by plan |

Full CSV: [seedance-2-5-pricing.csv](seedance-2-5-pricing.csv)

## The trap this table exposes

Credit counts are **not comparable across platforms**. Dreamina's 37 credits/sec and Kie's 63 credits/sec look similar, but because their credits are worth different amounts ($0.000184 vs $0.005), the real per-second cost differs by about 27×. Always compare **dollars per second**, never credit counts.

Also included: Kie's reference-video discount (480p drops 28 → 17, 720p 63 → 38, 1080p 158 → 95 credits/sec) — image-to-video undercuts text-to-video by roughly 40%.

## Sources

- Dreamina: https://dreamina.capcut.com/
- OpenRouter: https://openrouter.ai/bytedance/seedance-2.5
- Kie.ai: https://kie.ai/blog/seedance-2-5-pricing

Prices checked November 2026. This category reprices often — verify before buying.

## Full analysis

For the complete guide — including worked cost examples (what 10 test clips cost on each route) and the free-tier traps (why 80 free credits can't run one clip) — see the full review at **[Prismstead: Seedance 2.5 Specs, How to Use & Pricing](https://prismstead.com/seedance-2-5/)**.

## License

CC BY 4.0. Attribute to Prismstead (https://prismstead.com/) with a link.
