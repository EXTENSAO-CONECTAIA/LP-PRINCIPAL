# LP-PRINCIPAL — fonte/rascunho da landing do ConectaIA

## ⚠️ AVISO IMPORTANTE — leia antes de editar

**Este repositório NÃO é o que está em produção.**

A página visível em `https://www.direitohub.com.br/conectaia` é servida
pelo repositório `dhV2`, do arquivo:

```
dhV2/frontend/public/conectaia/index.html
```

Esse repositório aqui (`LP-PRINCIPAL`) é o **rascunho original** da
landing — uma versão simplificada que serviu de base. A versão em
produção foi expandida e tem **mais seções**, então **não dá para
copiar/colar de um lado pro outro**.

## Onde mexer

| Quero alterar... | Mexa em... |
|---|---|
| Algo que aparece em **`www.direitohub.com.br/conectaia`** | **`dhV2/frontend/public/conectaia/index.html`** |
| Apenas o rascunho histórico | aqui (`LP-PRINCIPAL`) |
| Auth/login da extensão | `dhV2` ou repositório da extensão |

## Diferenças entre as duas versões

| | `LP-PRINCIPAL/landing-page.html` | `dhV2/.../conectaia/index.html` |
|---|---|---|
| Linhas | ~1.200 | ~2.700 |
| Seções | 6 | 10+ |
| Hospedagem | — (não publicado) | **Azure Static Web Apps** |
| Domínio | — | `direitohub.com.br/conectaia` |

## Fluxo de deploy do que está no ar

```
GitHub Actions (.github/workflows/azure-static-web-apps-*.yml)
        │
        ▼
  Azure Static Web Apps
        │
        ▼
  white-sand-0e9a11010.1.azurestaticapps.net
        │
        ▼
  www.direitohub.com.br  (CNAME)
```

Toda vez que algo for mergeado em `dhV2/main`, o GitHub Actions builda
o React app + copia o conteúdo de `frontend/public/` (inclusive
`conectaia/`) e publica no Azure. Em ~3min está no ar.

## Como confirmar onde está hospedado

```bash
nslookup www.direitohub.com.br
# www.direitohub.com.br → white-sand-0e9a11010.1.azurestaticapps.net
#                       → azurestaticapps1.trafficmanager.net
#                       → ...azurewebsites.net
```
