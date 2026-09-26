# EstacionaFácil - Estrutura de Dados II

## Analytics

Plataforma web para gestão e análise de feedbacks de clientes de um estacionamento. O sistema recebe avaliações manualmente ou por arquivo CSV, classifica o serviço, identifica o sentimento e temas recorrentes e apresenta indicadores para apoiar a gestão operacional.

## Objetivo do projeto

O EstacionaFácil amplia continuamente seu portfólio, mas a leitura manual de avaliações dificulta identificar problemas e oportunidades. A plataforma organiza os feedbacks em um banco relacional, processa seu conteúdo com regras explicáveis em português e oferece um painel gerencial protegido por autenticação.

## Backlog

| Requisito | Função | Status |
|---|---|---|
| RF02 | Classificar os feedbacks dos clientes por categoria de serviço | Em andamento |
| RF06 | Emitir alertas automáticos quando o índice de satisfação de algum serviço cair abaixo de um limiar configurado | Em andamento |
| RF07 | Permitir filtragem das análises por período, tipo de contrato e categoria de veículo | Em andamento |

Serão feitos somente os Requisitos Funcionais, de acordo com o pedido da equipe.

## Tecnologias

| Camada | Tecnologia |
|---|---|
| Interface | React 19, Vite, Tailwind CSS 4, shadcn/ui |
| Gráficos | Recharts |
| Backend | Node.js, Express, tRPC 11 |
| Banco | MySQL/TiDB com Drizzle ORM |
| Qualidade | TypeScript e Vitest |

## Estrutura principal

`client/` contém a interface e as páginas do painel. `server/` contém as procedures tRPC, consultas ao banco e o classificador de feedbacks. `drizzle/` contém o schema e as migrações SQL. `docs/` contém o modelo de dados, o guia de instalação e o manual resumido.

## Formato do CSV

O importador aceita separadores vírgula ou ponto e vírgula. A primeira linha deve conter cabeçalhos. O campo textual pode ser chamado `feedback`, `comentario`, `comentário`, `texto` ou `comentario do cliente`; os campos opcionais podem ser `data` e `nota`.

```csv
feedback,data,nota
"Atendimento rápido e vaga segura",2026-08-31,5
```

Os exemplos acima servem apenas para documentar o formato. O repositório não contém avaliações fictícias ou depoimentos simulados.

## Critérios de aceite implementados

O painel exige autenticação, grava avaliações no banco, processa o texto, mostra histórico, calcula distribuição de sentimentos e satisfação média, permite importação CSV de até 1.000 linhas, oferece telas de alertas e configurações e mantém os artefatos de documentação no repositório.

## Equipe

| Membro | Função |
|---|---|
| Marco Antonio | Líder |
| Vicenzo Burti | Vice-Lider |
| Pedro Falsetti | Desenvolvedor |
| Gustavo Ramiro | Desenvolvedor |
| Romar | Desenvolvedor |
| Victor | Desenvolvedor |
| Prof Dawilmar | Colaborador |
