# Plano de validação

A planilha registra uma prova de conceito futura para PostgreSQL e Parquet. O roteiro abaixo detalha essa entrega como **proposta de trabalho**. Não há benchmark executado ou responsáveis atribuídos no material de origem.

## Entregas e critérios de conclusão

| Ordem | Entrega | Evidência para concluir | Dependência |
|---|---|---|---|
| 1 | Inventário verificável de F1–F3 | URL de cada recurso, data de coleta, período coberto, tamanho e esquema real | Acesso às fontes |
| 2 | Perfilamento e viabilidade dos indicadores | Contagens, chaves, nulos, duplicatas e campos disponíveis para Q1–Q8 | Inventário |
| 3 | Modelo revisado | Dicionário de campos e relacionamentos demonstrados com amostras | Perfilamento |
| 4 | Recorte completo do pipeline | Uma carga da coleta até um indicador, com relatório de qualidade | Modelo e regras de cálculo |
| 5 | Comparação de armazenamento e consultas | Medições reproduzíveis em CSV, Parquet e PostgreSQL | Recorte validado |
| 6 | Revisão do ADR-001 | Resultados, limitações e decisão da equipe registrados | Prova de conceito |

O responsável e o prazo de cada entrega estão **a definir**. A ordem indica dependências, sem estabelecer um cronograma que não consta na planilha.

## Prova de conceito de armazenamento

Usar o mesmo recorte de dados e as mesmas regras de limpeza para comparar formatos. Registrar quantidade de linhas, colunas, períodos e tamanho dos arquivos. Para PostgreSQL, informar também índices e espaço ocupado pelas tabelas.

Selecionar consultas representativas do [catálogo de indicadores](indicadores.md), começando pela contagem de turmas por componente e semestre. Consultas de ocupação só devem entrar se vagas e matrículas estiverem disponíveis e vinculadas.

Registrar ambiente, versões das ferramentas, consulta ou script executado, número de repetições e condição de cache. Separar tempo de leitura, transformação, carga e consulta quando aplicável. Comparar primeiro os resultados retornados; uma consulta mais rápida com totais diferentes não valida a arquitetura.

| Medição | CSV | Parquet | PostgreSQL |
|---|---|---|---|
| Recorte e quantidade de registros | A medir | Mesmo recorte | Mesmo recorte |
| Tamanho armazenado | A medir | A medir | A medir, incluindo índices |
| Tempo da consulta representativa | A medir | A medir com leitor informado | A medir com SQL e índices informados |
| Resultado conferido | Pendente | Pendente | Pendente |

## Verificação operacional

- Reexecutar a mesma carga e conferir que os totais não mudam por duplicação.
- Simular arquivo vazio ou coluna obrigatória ausente e conferir a interrupção da etapa.
- Simular falha antes da publicação e verificar que o consumidor continua vendo uma versão íntegra.
- Conferir manualmente uma amostra dos indicadores e registrar a versão dos dados usada.

## Quando revisitar a escolha

O ADR prevê revisão se consultas analíticas ultrapassarem aproximadamente **5 segundos**, se o volume ou o custo de manutenção crescerem, se as fontes mudarem significativamente ou se surgir necessidade de tempo real.

Esse valor é uma **meta da planilha**, não uma medição já alcançada. A aceitação do ADR depende da avaliação da equipe sobre as evidências; não ocorre automaticamente após a execução da prova de conceito.
