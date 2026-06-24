# Lorentz Orbitall — Documentação

Site de documentação do **Lorentz Orbitall** (Lorentz Supervisor), solução de gestão e monitoramento de Call Center CTI da Megatronix — administração, atendimento, discagem preditiva, gravação de chamadas e relatórios, com integração a Lorentz Server (CTI), Lorentz Cliente, 3CX e Asterisk.

Gerado com [MkDocs](https://www.mkdocs.org/) + [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

```
 _                         _
| |    ___  _ __ ___ _ __ | |_ ____
| |   / _ \| '__/ _ \ '_ \| __|_  /
| |__| (_) | | |  __/ | | | |_ / /
|_____\___/|_|  \___|_| |_|\__/___|

 ____                              _
/ ___| _   _ _ __   ___ _ ____   _(_)___  ___  _ __
\___ \| | | | '_ \ / _ \ '__\ \ / / / __|/ _ \| '__|
 ___) | |_| | |_) |  __/ |   \ V /| \__ \ (_) | |
|____/ \__,_| .__/ \___|_|    \_/ |_|___/\___/|_|
            | |

```

## Estrutura do conteúdo

A navegação (`mkdocs.yml`) está organizada em:

- **Administração** — configurações, funcionários, grupos, call center (agentes, ramais, fluxo, qualificação, script), estrutura funcional, permissões, tabelas de agenda e contato.
- **Gerenciamento** — agenda, campanha, cliente, monitoramento.
- **Lorentz Supervisor** — controles, configurações, discagem preditiva, organograma, FAQ.
  - **Lorentz Server (CTI)** — documentação técnica, fluxo de sistema, entidades, API Web Agent.
  - **Lorentz Cliente** — visão geral, discador preditivo + 3CX, configuração (INI), gravação de chamadas.
- **Relatórios** — chamadas, atendimentos, produtividade, qualificação.

## Comandos

```bash
yarn dev       # mkdocs serve — live-reload em http://localhost:8000
yarn build     # mkdocs build -d public
yarn copy      # copy.ps1 — sincroniza build com o projeto supervisor3cx (D:/app_lorentz)
yarn publish   # publish.ps1 — commit + push do conteúdo de /public
```

Comandos `mkdocs` diretos:

```bash
mkdocs serve   # servidor com live-reload
mkdocs build   # gera o site estático em ./site
mkdocs gh-deploy
mkdocs -h
```

## Deploy

- **CI:** [.github/workflows/docs.yml](.github/workflows/docs.yml) builda com `mkdocs build` ao alterar `docs/**` ou `mkdocs.yml`, e publica o artefato `site` na Vercel (`VERCEL_TOKEN`, `VERCEL_ORG_ID`, `VERCEL_PROJECT_ID`).
- **Local:** `publish.ps1` faz commit/push manual do diretório `public` gerado.
- Repositório do produto (Lorentz Supervisor / supervisor3cx): https://github.com/megatronix-lorentz/supervisor3cx/

## Ferramentas de manutenção

- [tools/icon_audit.py](tools/icon_audit.py) — audita o uso de ícones (`:material-...:` / `:fontawesome-...:`) na documentação. Veja convenções em [ICONOS.md](ICONOS.md).
  ```bash
  python tools/icon_audit.py --report icons_report.csv
  ```
- [tools/relatorios_link_check.py](tools/relatorios_link_check.py) — verifica links internos da seção de relatórios.

## Versões de referência

```
Python: 3.11.4
mkdocs: >=1.4.2
mkdocs-material: 9.1.6
mike: 1.1.2
```

Veja [requirements.txt](requirements.txt) para a lista completa de dependências Python.

## Estrutura do projeto

```
mkdocs.yml          # configuração principal (nav, tema, plugins)
docs/                # páginas em Markdown
    index.md          # página inicial
    images/           # imagens
    assets/            # style.css / style.js
overrides/           # customizações do tema (material/overrides)
tools/               # scripts de auditoria e manutenção
```

## Tema e ícones

- Tema: [mkdocs-material](https://github.com/squidfunk/mkdocs-material)
- Convenções de ícones: [ICONOS.md](ICONOS.md) — `:material-...:` para UI, `:fontawesome-brands-...:` apenas para marcas/redes sociais.
- [Ícones e emojis do Material](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/#using-emojis) · [Octicons](https://primer.style/foundations/icons/)

## Contato

- Rede Social: [@megatronix](https://www.instagram.com/megatronixoficial/)
- Telefone: (11) 3021-5561 — Nilson
- Celular: (11) 9-8223-9345 — Nilson
- [nilson@megatronix.com.br](mailto:nilson@megatronix.com.br)
- [www.megatronix.com.br](http://www.megatronix.com.br)
