# Fontes de Dados Abertos

Repositório de **dados** do directório [Solus Machina](https://solusmachina.net): as **fontes**
(serviços, APIs, portais e projectos digitais públicos) e os respectivos **ícones**.

---

## Papel deste repositório

O objectivo é reunir informação dispersa num directório simples, pesquisável e útil para cidadãos, jornalistas, investigadores e programadores. Curado para fontes oficiais e públicas, assim como projectos abertos de interesse público que utilizem fontes públicas e oficiais.

Lista completa das fontes: [FONTES.md](FONTES.md)

---

## Estrutura


| Pasta | Conteúdo |
| --- | --- |
| `sources/` | Uma fonte por ficheiro. O nome do ficheiro é o `id` mais `.json`. |
| `icons/` | Um ícone por fonte, com o nome do `id` e em SVG. |

---

## Contrato de uma fonte

Cada fonte é um ficheiro `sources/<id>.json`. O `id` tem de coincidir com o nome do
ficheiro (sem `.json`) e ser um slug em `kebab-case`.

```json
{
  "id": "dados-gov-pt",
  "name": "dados.gov.pt",
  "url": "https://dados.gov.pt",
  "description": "Portal oficial de dados abertos do Estado português, com catálogo de conjuntos de dados publicados por entidades públicas.",
  "icon": "/icons/dados-gov-pt.svg",
  "location": "portugal",
  "tags": ["dados-abertos", "transparencia", "administracao-publica", "gov", "catalogo"],
  "categories": ["dados"],
  "active": true
}
```

| Campo | Obrigatório | Regras |
| --- | --- | --- |
| `id` | sim | Único; slug `kebab-case`; igual ao nome do ficheiro. |
| `name` | sim | Nome público da fonte. |
| `url` | sim | URL canónica; começa por `http://` ou `https://` (HTTPS preferível). |
| `description` | sim | Curta e factual (1–2 frases). |
| `icon` | sim | Caminho público em `/icons/`; o ficheiro tem de existir em `icons/`. |
| `location` | sim | `portugal` ou `europa`. |
| `tags` | sim | Array de slugs `kebab-case`, sem acentos (`emergencia`, não `emergência`). |
| `categories` | sim | Array não vazio e sem repetições, de `api`, `dados`, `servico`. |
| `active` | não | Default `true`. Com `false`, a fonte é ignorada na listagem. |


---

## Regras dos ícones

- Um ficheiro por fonte, com o nome do `id`: `icons/<id>.svg`.
- **O SVG tem de ser estático.**.
- `icons/source-generic.svg` é o ícone genérico das fontes que ainda não têm identidade
  visual própria. Não o remover.

---

## Como contribuir

1. Faz fork do projecto.
2. Cria uma branch para a tua adição:
   ```bash
   git checkout -b add/nome-da-fonte
   ```
3. Faz commit das tuas alterações:
   ```bash
   git commit -am 'feat: adiciona fonte nome-da-fonte'
   ```
4. Faz push da tua branch:
   ```bash
   git push origin add/nome-da-fonte
   ```
5. Cria um novo Pull Request.

### Acrescentar ou corrigir uma fonte

Criar ou editar `sources/<id>.json` conforme o contrato acima.

Para o ícone, acrescentar `icons/<id>.svg` e mudar o campo `icon` da fonte para
`/icons/<id>.svg`. As duas coisas têm de vir no mesmo pull request, senão a validação
falha por o ícone não corresponder ao ficheiro.

---

## Convenções

- Commits: Conventional Commits (`feat:`, `fix:`, `docs:`, …)
- Branch principal: `main`
- Tags e `id` em `kebab-case` sem acentos
- Texto em português europeu

---

## Critérios de inclusão

Fontes devem ser serviços ou projectos digitais **públicos** (ou de interesse público)
com presença online, relevantes para Portugal ou para a Europa — oficiais, civis,
académicos ou comunitários. Preferir fontes estáveis e URLs canónicas.
