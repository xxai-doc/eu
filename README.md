<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Webgunearen kodearen zati bat kode irekikoa da, ongi etorria itzulpena optimizatzen laguntzeko.

## frontend kodea

* [frontend kodea](https://github.com/xxai-art/web)
* [Gune osorako hizkuntza paketeak](https://github.com/xxai-art/web/tree/main/i18n)
* [Saioa hasteko moduluen hizkuntza paketeak](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Webgunea Dokumentazio eleaniztuna](https://github.com/xxai-doc)

Front-end programazio-lengoaia [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) da, eta coffeescript sintaxian oinarritutako ezaugarri batzuk gehitzen ditu, ikus [./coffee_plus.md](./coffee_plus.md) .

## Webguneen eta dokumentuen nazioartekotzea

Eraiki ondorengo 3 proiektuetan

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Atzizkia `.mdt` da, `<+ ./coffee_plus/import.js>` antzeko sintaxia erabil dezakezu kanpoko fitxategiak aipatzeko eta `.md` atzizkiarekin markdown sortu.

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Markdown itzulpenak ez ditu kodeak eta estekak itzuliko, eta itzulitako esaldiak gordeko ditu. Itzulpena aldatzen bada baina jatorrizko testua aldatzen ez bada, berriro exekutatzeak ez du itzulpenaren aldaketa gainidatziko.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  `yaml` sortutako webguneak itzultzeko hizkuntza-fitxategiak.

### Dokumentuen Itzulpena Automatizatzeko Argibideak

Ikus [xxai-art/doc](https://github.com/xxai-art/doc) biltegia

Lehenengo nodejs, [direnv](https://direnv.net) eta [bun](https://github.com/oven-sh/bun) instalatzea gomendatzen da, eta gero `direnv allow` exekutatu direktorioa sartu ondoren.

Ehunka hizkuntzatara itzulitako biltegi handiegiak ekiditeko, hizkuntza bakoitzerako kode-biltegi bereizia sortu nuen eta biltegi hau gordetzeko erakunde bat sortu nuen.

`GITHUB_ACCESS_TOKEN` ingurune-aldagaia ezarriz eta, ondoren, [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) exekutatuz gero, biltegia automatikoki sortuko da.

Jakina, biltegi batean ere jar dezakezu.

Itzulpen script erreferentzia [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Script kodea honela interpretatzen da:

[bunx](https://bun.sh/docs/cli/bunx) npx-ren ordezkoa da, azkarragoa dena. Noski, bun instalatuta ez baduzu, ordez `npx` erabil dezakezu.

`bunx mdt zh` k `.mdt` errendatzen du zh direktorioan `.md` gisa, ikusi beheko estekatutako 2 fitxategiak

* [kafea_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [kafea_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` da itzulpenaren oinarrizko kodea ( `nodejs` instalatuta bakarrik baduzu, baina `bun` eta `direnv` instalatuta ez badaude, `npx i18n` ere exekutatu dezakezu itzultzeko).

[i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) analizatuko du, dokumentu honetan `i18n.yml` ren konfigurazioa honako hau da:

```
en:
zh: ja ko en
```

Esanahia hau da: txinera itzulpena japonierara, koreera, ingelesa, ingelesa beste hizkuntza guztietara. Txinera eta ingelesa bakarrik onartu nahi badituzu, `zh: en` idatz dezakezu.

Azkena [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) da, eta hizkuntza bakoitzaren `README.md` ren izenburu nagusiaren eta lehen azpitituluaren arteko edukia ateratzen du sarrera bat sortzeko `README.md` . Kodea oso erraza da, zuk zeuk begiratu dezakezu.

Google APIa doako itzulpenetarako erabiltzen da. Ezin baduzu Google-ra sartu, mesedez konfiguratu eta ezarri proxy bat, hala nola:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Itzulpen script-ak itzulpen-cache bat sortuko du `.i18n` direktorioan, mesedez egiaztatu `git status` eta gehitu kode biltegian itzulpen errepikatuak saihesteko.
