# Boulder Zeeland — interesse-check

Landingspagina om te peilen hoeveel animo er is voor een boulderhal in Zeeland,
bedoeld om te koppelen aan een QR-code op flyers/stickers. Statische site,
geen backend nodig — draait direct op GitHub Pages.

## Live site

Na het aanzetten van GitHub Pages (zie onder): `https://<jouw-github-gebruikersnaam>.github.io/boulder-zeeland/`

## Setup die je zelf nog moet doen

### 1. Google Form aanmaken

Maak een nieuwe Google Form met deze vragen (zo blijft het consistent met de
teksten op de pagina):

1. **Titel:** Boulder Zeeland — interesseformulier
2. **Beschrijving:** "We gebruiken dit alleen om te bepalen of een boulderhal in Zeeland de moeite waard is. Geen spam, geen verkoop van je gegevens."
3. **Vraag 1** (Meerkeuze): *Hoe geïnteresseerd ben je in een boulder-/klimhal in Zeeland?*
   - Heel geïnteresseerd, ik zou meteen lid worden
   - Best geïnteresseerd, ik zou het proberen
   - Nieuwsgierig, weet het nog niet
   - Niet echt, ik vul dit voor iemand anders in
4. **Vraag 2** (Meerkeuze): *Wat is je ervaring met boulderen/klimmen?*
   - Nooit gedaan, maar wil het proberen
   - Af en toe, meestal op vakantie of bij vrienden
   - Regelmatig, ik zoek een vaste plek
   - Ervaren klimmer/boulderer
5. **Vraag 3** (Kort antwoord): *In welke plaats of met welke postcode woon je?*
6. **Vraag 4** (Kort antwoord, e-mailvalidatie aan): *E-mailadres (voor updates over een eventuele opening)*
7. **Vraag 5** (Paragraaf, optioneel): *Wat zou jou over de streep trekken om lid te worden?*

### 2. Form embedden op de site

In Google Forms: **Verzenden** → tabblad `<>` (embed HTML) → kopieer de
`src="..."` waarde. Open `index.html` en vervang **beide** voorkomens van
`https://docs.google.com/forms/d/e/PLACEHOLDER_FORM_ID/viewform...` (in de
`<iframe>` en in de fallback-link) met je eigen URL.

### 3. Bezoekersteller

De teller op de pagina gebruikt [CounterAPI](https://counterapi.dev) — een
gratis, no-signup hit counter. Hij werkt out-of-the-box zodra de site live
staat; je hoeft niets te registreren. Wil je een eigen namespace, wijzig dan
`namespace`/`counter` in het `<script>`-blok onderaan `index.html`.
Let op: dit is een gratis derde-partij dienst — als die ooit offline gaat,
verdwijnt de teller stilletjes (de pagina blijft gewoon werken, de teller
toont dan niets).

### 4. Contactgegevens in de footer

De footer bevat nu geen contact-e-mailadres — voeg er zelf een toe in
`index.html` als je wilt dat mensen je kunnen bereiken buiten het formulier om.

## GitHub Pages aanzetten

1. Push deze repo naar GitHub (publiek, anders werkt Pages niet gratis).
2. Ga naar **Settings → Pages**.
3. Bij **Source**: kies branch `main`, map `/ (root)`.
4. Na een paar minuten is de site live op de URL hierboven.

## Wijzigingen

Alles staat in één bestand: `index.html` (HTML, CSS en JS samen, geen build-stap).
