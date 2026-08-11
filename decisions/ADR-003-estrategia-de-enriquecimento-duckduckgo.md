# ADR-003: Estratégia de Enriquecimento de Dados com DuckDuckGo

## Status
Aceito

## Contexto
Após consultar o CNPJ na API Open CNPJ, o sistema deve enriquecer os dados da empresa usando informações encontradas na web: redes sociais, contatos, site institucional e tudo que for possível. A fonte de busca precisa ser gratuita e sem necessidade de chave de API.

## Decisão
Utilizar o **DuckDuckGo** como mecanismo de busca para o enriquecimento de dados, seguindo o fluxo:

1. Buscar no DuckDuckGo a **razão social** do CNPJ retornado pela Open CNPJ.
2. Refinar/complementar a busca usando **dados vindos da Open CNPJ** (email institucional, nome fantasia, telefone, endereço).
3. Coletar e estruturar os resultados: links para redes sociais, contatos, site oficial e demais informações disponíveis.

## Consequências
- Enriquecimento gratuito e sem chave de API.
- Os resultados são apenas *links/trechos* descobertos pela busca — a qualidade depende dos dados retornados pelo buscador.
- O serviço de enriquecimento fica isolado em `src/lib/`, separado do cliente da Open CNPJ.
- A coleta de conteúdo de páginas de terceiros (se adotada no futuro) deve ser avaliada quanto a termos de uso e confiabilidade.

## Alternativas consideradas
- **APIs de busca pagas (SerpAPI, Bing):** descartadas por custo incompatível com o portfólio.
- **Scraping direto de páginas de terceiros:** adiado por questões de termos de uso; o DuckDuckGo entrega links/metadados com menor risco.
