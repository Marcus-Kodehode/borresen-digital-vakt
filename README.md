# borresen-digital-vakt

Overvåking av [borresendigital.no](https://www.borresendigital.no) fra
utsiden. Siden overvåker seg selv med en Cloudflare Cron Trigger, men en
overvåker som stopper, sender ingen varsler. Disse jobbene står utenfor
Cloudflare og varsler på e-post fra GitHub når noe feiler.

| Workflow                                                           | Når               | Hva                                                                                                                                                                         |
| ------------------------------------------------------------------ | ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Vakthund](.github/workflows/vakthund.yml)                         | Hvert 30. minutt  | Pulsen fra cron-jobbene (`/api/drift/puls`), forsiden og robots.txt gjennom kanten, og at `http://` og adressen uten www går permanent til `https://www.borresendigital.no` |
| [Lighthouse mot produksjon](.github/workflows/lighthouse-prod.yml) | Hver natt         | Fem sider, desktop, median av tre. Ytelse ≥ 90, tilgjengelighet 100, beste praksis og SEO ≥ 90                                                                              |
| [Keepalive](.github/workflows/keepalive.yml)                       | Den 1. hver måned | Hindrer at GitHub slår av planlagte workflows etter 60 dager uten aktivitet                                                                                                 |

Repoet er offentlig fordi GitHub Actions er gratis i offentlige repoer. Alt
som sjekkes er offentlige adresser, og ingen jobber bruker hemmeligheter.

## Lisens

Koden er synlig, men ikke åpen kildekode. © 2026 Børresen Digital, alle
rettigheter forbeholdt. Den kan leses og lenkes til, men ikke kopieres,
endres eller brukes andre steder uten skriftlig tillatelse. Se
[LICENSE](LICENSE).

Sikkerhetsproblemer meldes på e-post, se [SECURITY.md](SECURITY.md).

Blogginnlegget
[«Jeg overvåker min egen side, og noe må overvåke det også»](https://www.borresendigital.no/nb/blogg/hvem-overvaaker-overvaakeren)
forteller hvorfor og hvordan.

---

[Børresen Digital](https://www.borresendigital.no)
