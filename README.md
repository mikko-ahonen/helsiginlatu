# Helsingin Latu ja Polku ry — GitHub Pages + Decap CMS

Jekyll-pohjainen staattinen sivusto GitHub Pagesilla, sisällönhallinta Decap CMS:llä.

## Pikaohje

### 1. Luo GitHub-repo ja julkaise

1. Luo uusi GitHub-repositorio
2. Pura tämä zip ja lataa tiedostot repositorion juureen
3. **Settings → Pages** → Source: `Deploy from a branch` → Branch: `main` / `/ (root)`

### 2. Lisää logo

Lataa logo osoitteesta:
```
https://helsinginlatu.fi/wp-content/uploads/2022/05/helapo_logo_350x90.jpg
```
Tallenna: `assets/images/helapo_logo_350x90.jpg`

### 3. Decap CMS -käyttöönotto

CMS löytyy osoitteesta `https://sivustosi.fi/admin/`.

**Vaihtoehto A: GitHub OAuth (suositeltava GitHub Pagesille)**

1. Muokkaa `admin/config.yml`: vaihda `OWNER/REPO` → oma käyttäjänimi/repo
2. Tarvitset OAuth-proxyn autentikointiin. Vaihtoehdot:
   - [Netlify OAuth](https://docs.netlify.com/visitor-access/oauth-provider-proxying/): Luo GitHub OAuth App (callback URL: `https://api.netlify.com/auth/done`), lisää Netlify-sivustolle Access-asetuksiin
   - [Cloudflare Workers OAuth proxy](https://github.com/sveltia/sveltia-cms-auth): Ilmainen vaihtoehto

**Vaihtoehto B: Netlify Identity (jos siirrät sivuston Netlifyyn)**

1. Kommentoi `admin/config.yml`:stä `github`-backend pois ja käytä `git-gateway`
2. Ota käyttöön Netlify Identity ja Git Gateway Netlify-sivuston asetuksista

### 4. Oma domain (helsinginlatu.fi)

1. Lisää repositorion juureen `CNAME`-tiedosto sisällöllä: `helsinginlatu.fi`
2. DNS-asetukset:
   - A-tietueet: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Tai CNAME: `www` → `käyttäjänimi.github.io`

## Rakenne

```
_config.yml              Jekyll-asetukset
_layouts/                Sivupohjat (default, home, page)
_includes/               Header, footer, navigaatio, CTA
_pages/                  Sisältösivut (markdown) — muokkaa CMS:stä
  jasenille/             Jäsenille-alasivut
  tietoa-meista/         Tietoa meistä -alasivut
  tule-mukaan/           Tule mukaan -alasivut
_data/events.yml         Tapahtumalista — muokkaa CMS:stä
assets/css/style.css     Tyylitiedosto
assets/images/           Kuvat
admin/                   Decap CMS
  index.html             CMS-sivu
  config.yml             CMS-asetukset ja kokoelmat
```

## Sisällön muokkaus

Kaikki sivut voi muokata Decap CMS:n kautta osoitteessa `/admin/`. CMS:ssä on seuraavat osiot:

- **Tapahtumat** — Etusivun ja Tapahtumat-sivun tapahtumalista
- **Pääsivut** — Tapahtumat, Liity jäseneksi, Yhteystiedot, Tietosuojaseloste
- **Jäsenille** — Kaikki jäsensivut
- **Tietoa meistä** — Yhdistyksen tietosivut
- **Tule mukaan** — Toimintasivut

Vaihtoehtoisesti voit muokata `_pages/`-kansion Markdown-tiedostoja suoraan GitHubissa.

## Paikallinen kehitys

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Sivusto: `http://localhost:4000`, CMS: `http://localhost:4000/admin/`
