# Glovo, measured against its own accessibility statement

**[Read the full report](https://noxquality.github.io/glovo-eaa-check/report.html)**  ·  [Español](LEEME.md)

> **Independent, unsolicited measurement, 8 October 2026.** Not affiliated with Glovo and
> not approved by Glovo. It measures the public product, the way anyone finds it without an
> account. It does not measure teams, it does not measure people, and no failure is
> attributed to anyone.

Glovo published an accessibility statement and committed in writing to WCAG 2.1 Level AA
and EN 301 549. That is the standard accessibility is measured against in Europe, so that
is the standard used here.

The five specific promises in that document were checked against the product, one by one.

## The five promises

| The promise, verbatim | Verdict | What holds it up or breaks it |
|---|---|---|
| Sufficient colour contrast between text and background | ✅ holds | 1 failure across 776 text nodes measured |
| Simple navigation, consistent headings and landmarks | ✅ holds | Missing a skip link, and the title on two pages |
| Clear and descriptive error notifications | 🟡 halfway | The required-options error is never announced |
| Keyboard accessibility | ❌ does not hold | The address field on the home page cannot be operated with a keyboard |
| Accessible labels on interactive elements | ❌ does not hold | 40 of 40 inputs in the product dialog have no accessible name |

The channel the statement offers for reporting a problem, support, does not open without an
account: the "Contact us" link in the footer is an anchor that fires nothing.

## Two findings outside the statement

**The fix reached restaurants and not shops.** With an entire category closed, the same
closed store behaves in two different ways depending on its vertical.

**Search answers anything with the same catalogue.** Searching "motosierra", Spanish for
chainsaw, returns 69% of the same stores as searching "pizza", with the same first result.

## What is in this repo

| file | what it is |
|---|---|
| [report.html](report.html) | the full report, with the evidence behind every point |
| [informe.html](informe.html) | the same report in Spanish |
| [evidencia/busqueda.md](evidencia/busqueda.md) | the seven-query search battery, with the method and the calculation (Spanish) |

## Method and limits, short version

Desktop web, Barcelona, no login, cookies declined, four pages plus two dialogs. Inspection
of the DOM and the accessibility tree, a keyboard pass counted Tab by Tab, and contrast
calculated on computed colour and background.

No real screen reader, no native app, no checkout, which requires an account. The full
limits are in the report.

This piece **makes no legal claim**. Whether a company meets a legal requirement is for a
regulator to decide, not for a private audit.

## Licence and authorship

Text and data under [CC BY 4.0](LICENSE). Made by
[Nox Quality Studio](https://noxquality.com), by sol.
