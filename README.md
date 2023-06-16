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
