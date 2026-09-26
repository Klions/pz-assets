# pz-assets

Imagens públicas das páginas da Steam Workshop dos mods de Project Zomboid do Klions. O código de cada mod fica no repositório dele (privado); aqui ficam só as imagens, para a descrição da Steam conseguir mostrá-las.

As imagens são servidas pelo [jsDelivr](https://www.jsdelivr.com/), uma CDN gratuita com servidores no mundo todo e sem limite de banda. Cada link fica assim:

```
https://cdn.jsdelivr.net/gh/Klions/pz-assets@main/<ModId>/<língua>/<arquivo>
```

Exemplo: https://cdn.jsdelivr.net/gh/Klions/pz-assets@main/SmartAnimalWaste/en/banner.gif

## Organização

```
<ModId>/            uma pasta por mod, com o mesmo nome do id do mod.info
  en/               imagens da descrição em inglês
  pt/               imagens da descrição em português
  preview.gif       miniatura animada da Oficina (512x512, até 1 MB)
SmartFarm/          logo da coleção SmartFarm (mods de fazenda automática)
  SmartFarm-White.png   para fundo escuro
  SmartFarm-Black.png   para fundo claro
```

Os mods da coleção SmartFarm levam o logo num canto livre de cada imagem, discreto, no branco ou no preto conforme o fundo.

## Regras

- Só imagens (PNG, GIF, JPG). Nada de código, arquivos de trabalho (.psd, .kra) ou vídeos.
- As imagens são geradas e enviadas pela ferramenta do repositório de cada mod. No Smart Animal Waste: `python tools/make_steam_art.py` gera e `python tools/publish_steam_images.py` copia para cá, faz commit e push, limpa o cache do jsDelivr dos arquivos alterados, confere cada link e troca os links na descrição.
- Mesmo nome com imagem nova exige limpar o cache do jsDelivr: `https://purge.jsdelivr.net/gh/Klions/pz-assets@main/<caminho>` (a ferramenta faz isso sozinha).
- A descrição da Steam tem limite de 8.000 caracteres, e cada link conta: nomes de pasta e de arquivo curtos.
- Não apague nem renomeie imagens já publicadas: a página da Steam de uma versão antiga continua apontando para elas.
