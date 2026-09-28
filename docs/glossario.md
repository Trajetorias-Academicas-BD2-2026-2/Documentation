# Glossário

| Termo | Significado |
|---|---|
| **ACID** | Garantias de transações: Atomicidade, Consistência, Isolamento e Durabilidade |
| **ADR** | *Architecture Decision Record* — registro de decisão arquitetural |
| **Coorte** | Grupo que compartilha um evento de referência, como ingresso no mesmo período |
| **Checksum** | Valor calculado a partir do arquivo para conferir integridade e identificar alterações |
| **CSV** | Formato de texto tabular com valores separados por vírgula ou ponto e vírgula |
| **Dado bruto** | Arquivo original, exatamente como veio da fonte |
| **Desnormalizado** | Tabela que repete ou consolida dados para acelerar consultas |
| **ELT** | *Extract, Load, Transform* — carrega primeiro, transforma depois |
| **ETL** | *Extract, Transform, Load* — transforma antes de carregar |
| **Granularidade** | Nível representado por cada registro, como componente + período + turno |
| **Idempotência** | Repetir uma carga com a mesma entrada sem duplicar ou alterar indevidamente o resultado |
| **LGPD** | Lei Geral de Proteção de Dados Pessoais (Lei nº 13.709/2018) |
| **Lote (batch)** | Processamento em janelas periódicas, em vez de contínuo |
| **Normalizado** | Tabela organizada para evitar duplicação de informação |
| **OLAP** | Carga analítica: poucas consultas pesadas, com agregações |
| **OLTP** | Carga transacional: muitas operações pequenas e rápidas |
| **Parquet** | Formato binário colunar para dados analíticos |
| **Pipeline** | Caminho que o dado percorre da origem ao consumo |
| **PoC** | *Proof of concept* — prova de conceito |
| **SGBD** | Sistema Gerenciador de Banco de Dados |
| **SIGAA** | Sistema Integrado de Gestão de Atividades Acadêmicas |
| **Vazão** | Volume de dados que chega por unidade de tempo |

**Referências:** Reis & Housley, *Fundamentos de Engenharia de Dados* (Novatec, 2023);
Kleppmann, *Designing Data-Intensive Applications*; apresentação "Engenharia de Dados 101" (BD2),
adaptada de Chip Huyen, CS 329S — Stanford.
