# Fortuna — Public Pages

Static GitHub Pages site for the Fortuna iOS app, hosting the legal and support pages required by the Apple App Store. Adapted from the [voxxo-landing](https://github.com/borabafli/voxxo-landing) template.

## Pages

| Path | Purpose |
|------|---------|
| `index.html` | Landing page linking to all sub-pages. |
| `privacy.html` | Gizlilik Politikası (KVKK + GDPR aligned). Mirrors the in-app copy in `apps/mobile/src/copy/tr.ts` (`privacy.detail`). |
| `terms.html` | Kullanım Şartları (incl. auto-renewing Fortuna Mystic subscription + jeton disclosure & EULA reference). |
| `support.html` | Support / FAQ — required as the App Store "Support URL". |
| `account-deletion.html` | Account & data deletion instructions — required by App Store guideline 5.1.1(v). |
| `404.html` | Friendly 404 fallback. |

All pages are in Turkish (`lang="tr"`), matching Fortuna's Turkish-market, Turkish-only user-facing copy convention (see the main repo's `CLAUDE.md` §4).

## How to publish

1. Create a new public GitHub repository named `fortuna-app-github-page` under the `Lorem-Software` organisation.
2. Commit the contents of this folder to the repo's `main` branch.
3. In **Settings → Pages**, set the source to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Wait ~1 minute for the first deploy. Pages will be live at:

   ```
   https://lorem-software.github.io/fortuna-app-github-page/
   ```

## App Store Connect — required URLs

When submitting Fortuna, paste these into App Store Connect:

- **Privacy Policy URL:** `https://lorem-software.github.io/fortuna-app-github-page/privacy.html`
- **Support URL:** `https://lorem-software.github.io/fortuna-app-github-page/support.html`
- **Marketing URL** (optional): `https://lorem-software.github.io/fortuna-app-github-page/`
- **EULA:** leave blank to use Apple's standard EULA — our Terms reference it explicitly.

## Keeping this in sync with the app

`privacy.html` §1–13 mirrors the KVKK/gizlilik copy shipped in-app
(`apps/mobile/src/copy/tr.ts` → `privacy.detail`). If that copy changes,
update both places. Note: as of this page's publish date, the in-app §1
still has a placeholder line ("adres bilgileri … yayın aşamasında
güncellenecektir") — this page fills in the real controller address; the
in-app copy should be updated to match on the next mobile release.

`privacy.html` §6 lists AWS, OpenAI, Anthropic, ElevenLabs, RevenueCat,
Apple, and Google as sub-processors — this is copied verbatim from the
shipped in-app text. `CLAUDE.md` (the backend source of truth) currently
describes the AI stack as Bedrock-only (no direct OpenAI/Anthropic API
keys) with Polly as the default TTS provider (ElevenLabs optional/env-var
gated). Reconcile which is accurate before App Store submission.

## Owner / contact

Lorem Software · Mert Zeybek<br/>
Değirmendere, Kuşadası, Aydın, Türkiye<br/>
privacy@lorem.software
