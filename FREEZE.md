# FREEZE

A zh1-ready tag a freeze commit(ek) utáni main csúcsot jelöli.

| Mező | Érték |
|------|-------|
| Repository | https://github.com/MrBombOn/adatb2-zh1-segedlet |
| Branch | main |
| Visibility | PUBLIC |
| Freeze dátum (local) | 2026-10-06 07:51:19 +0200 |
| Tartalom kész commit | 9645ba3ea0710c15c0e153e685a4513d8eef0947 |
| Fájlok száma | 124 |
| Tag | zh1-ready |

## Mit jelent a freeze?

- A ZH1 segédlet tartalma ezen a tagon **késznek tekintett**.
- További javítások új commitokban mehetnek; a zh1-ready a leadási pillanatot jelöli.
- Nincs secret, Moodle anyag, kurzus PDF.

## Ellenőrzés

`	ext
git fetch --tags
git checkout zh1-ready
`
