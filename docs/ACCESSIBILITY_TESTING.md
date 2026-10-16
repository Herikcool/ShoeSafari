# Storefront accessibility checks

The `Storefront accessibility checks` CI job runs axe-core against the shop, login, cart dialog, and checkout routes using local fixture data. The shop's existing `__shoesafari_e2e` fixture avoids Firestore, and checkout's quote endpoint is mocked; the checks do not need Firebase credentials or a connected wallet.

The scan covers WCAG 2.0/2.1 A and AA plus WCAG 2.2 AA. Critical and serious axe findings fail CI. Moderate and minor findings are printed as informational output so the baseline can be introduced without hiding them; they do not currently block the job. These checks cover the initial rendered state only and do not replace keyboard, screen-reader, color-contrast-in-context, or manual checkout testing. Update this document when changing the route fixtures, WCAG tags, or blocking impact levels.

To run the same checks locally, install the project's dependencies and Chromium once, then run `npm run test:e2e:accessibility`.
