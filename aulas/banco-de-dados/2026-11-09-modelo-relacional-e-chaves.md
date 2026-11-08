# Aula — Banco de Dados: modelo relacional e chaves

- **Disciplina:** Banco de Dados
- **Data de preparação:** 2026-11-08
- **Data da sessão:** 2026-11-09
- **Duração prevista:** 45 minutos
- **Tema:** Relações, atributos, tuplas, esquemas, chaves e integridade referencial
- **Status:** Material preparado; estudo pendente

Esta parte compõe, com a aula de [Fundamentos de Engenharia de Software e ciclo de vida](../engenharia-de-software/2026-11-09-fundamentos-e-ciclo-de-vida.md), a sessão de TI de segunda-feira, com 90 minutos previstos.

## 1. Objetivos

Ao final desta parte, você deverá conseguir:

1. Identificar os principais elementos do modelo relacional.
2. Distinguir tabela, linha, coluna, esquema e domínio.
3. Reconhecer chaves primárias e estrangeiras, inclusive em exemplos simples.
4. Explicar a finalidade das restrições de integridade mais básicas.

## 2. Pré-requisitos

- Não é necessário conhecimento prévio de teoria de banco de dados.
- Familiaridade com sistemas e estruturas de dados ajuda, mas não é exigida.

## 3. Roteiro — 45 minutos

| Etapa | Tempo |
|---|---:|
| Objetivos e analogia com cadastro | 3 min |
| Conceitos do modelo relacional | 10 min |
| Chaves e relacionamentos | 12 min |
| Integridade e exemplos | 8 min |
| Questões e revisão | 12 min |
| **Total** | **45 min** |

## 4. O que é um banco de dados?

Um **banco de dados** é uma coleção organizada de dados relacionados, mantida para que possam ser consultados e atualizados de forma controlada. Um **Sistema Gerenciador de Banco de Dados (SGBD)** é o software que permite definir, armazenar, consultar, modificar e administrar esses dados.

Analogia: pense em um arquivo organizado de uma instituição. O banco de dados corresponde às informações organizadas; o SGBD oferece os mecanismos para localizar, registrar e proteger essas informações.

Nesta aula, o foco é o **modelo relacional**, que organiza dados em relações, geralmente representadas por tabelas.

## 5. Vocabulário relacional

Considere a tabela abaixo:

### PESSOA

| id_pessoa | nome | email |
|---:|---|---|
| 101 | Ana | ana@example.org |
| 102 | Rui | rui@example.org |

No modelo relacional:

- **Relação:** estrutura que representa um conjunto de dados relacionados; costuma ser apresentada como tabela.
- **Tupla:** uma ocorrência dentro da relação; em uma tabela, corresponde didaticamente a uma linha.
- **Atributo:** característica descrita pela relação; em uma tabela, corresponde a uma coluna.
- **Domínio:** conjunto de valores permitidos para um atributo. Por exemplo, `id_pessoa` pode aceitar inteiros positivos; uma situação cadastral pode aceitar apenas valores definidos.
- **Esquema:** definição da estrutura da relação, como nome dos atributos e regras aplicáveis.
- **Instância:** conjunto de dados que está armazenado em determinado momento.

**Cuidado com os termos:** em materiais introdutórios, “tabela”, “linha” e “coluna” costumam ser usados como analogias de relação, tupla e atributo. Em provas, os termos formais podem aparecer diretamente.

## 6. Chaves: como identificar registros e relacioná-los

Uma chave permite identificar uma tupla ou estabelecer uma relação entre conjuntos de dados.

### Chave candidata

É um atributo, ou conjunto de atributos, capaz de identificar unicamente cada tupla, sem atributos desnecessários. Uma relação pode ter mais de uma chave candidata.

No exemplo de PESSOA, se o sistema exige que cada `id_pessoa` e cada `email` sejam únicos, ambos podem ser candidatos a identificar os registros.

### Chave primária (primary key)

É a chave candidata escolhida para identificar cada tupla da relação.

- Seus valores devem ser únicos.
- Não pode ser nula.
- Pode ser simples (um atributo) ou composta (mais de um atributo).

Uma chave primária composta poderia ser `(id_turma, id_aluno)` em uma tabela de matrículas, caso a combinação identifique uma matrícula e o mesmo aluno possa aparecer em diferentes turmas.

### Chave estrangeira (foreign key)

É um atributo, ou conjunto de atributos, que referencia uma chave de outra relação (ou, conforme o projeto, da própria relação).

Exemplo:

### PEDIDO

| id_pedido | id_pessoa |
|---:|---:|
| 5001 | 101 |
| 5002 | 102 |

`PEDIDO.id_pessoa` pode ser uma chave estrangeira que referencia `PESSOA.id_pessoa`. Assim, cada pedido fica associado a uma pessoa existente, conforme as regras definidas.

**Atenção:** uma chave estrangeira não precisa, por si só, ser única. Uma pessoa pode fazer vários pedidos, então o mesmo `id_pessoa` pode aparecer em várias linhas de PEDIDO.

## 7. Integridade dos dados

As restrições de integridade ajudam a impedir que a base armazene combinações inválidas.

- **Integridade de entidade:** a chave primária identifica cada tupla; por isso, seus valores são únicos e não nulos.
- **Integridade referencial:** um valor de chave estrangeira deve corresponder a uma chave referenciada existente, ou seguir a regra definida para valores nulos.
- **Integridade de domínio:** os valores de um atributo devem respeitar o domínio e as restrições associadas, como tipo, faixa ou conjunto permitido.

Essas regras são diferentes de regras de negócio mais amplas. Por exemplo, “um pedido deve ser aprovado em até dois dias” pode ser uma regra de negócio; “a data de criação deve ser válida” é uma restrição sobre os dados.

## 8. Exemplo integrado

Imagine duas relações:

- `PESSOA(id_pessoa, nome, email)`
- `PEDIDO(id_pedido, id_pessoa, data_pedido)`

Uma modelagem inicial pode definir:

- `PESSOA.id_pessoa` como chave primária;
- `PEDIDO.id_pedido` como chave primária;
- `PEDIDO.id_pessoa` como chave estrangeira que referencia `PESSOA.id_pessoa`.

Essa estrutura permite associar vários pedidos a uma pessoa sem repetir os dados de nome e e-mail em cada pedido. Também permite verificar se a pessoa referenciada existe.

## 9. Resumo essencial

- Relação é apresentada normalmente como tabela; tupla como linha; atributo como coluna.
- Domínio define os valores permitidos para um atributo.
- Esquema descreve a estrutura; instância são os dados presentes em determinado momento.
- Chave primária identifica unicamente uma tupla e não admite valor nulo.
- Chave estrangeira referencia uma chave de outra relação; pode repetir-se quando vários registros apontam para o mesmo registro referenciado.
- Integridade de entidade, referencial e de domínio protegem aspectos diferentes da consistência dos dados.

## 10. Questões de fixação

Questões autorais para treinamento, não atribuídas a banca ou prova específica. Responda antes de consultar materiais externos; o gabarito será comentado após sua tentativa.

### Questão 1

No modelo relacional, uma linha de uma tabela é normalmente chamada de:

- A. atributo.
- B. domínio.
- C. tupla.
- D. esquema.

### Questão 2

Uma tabela `PEDIDO` possui o atributo `id_cliente`, que referencia a chave primária da tabela `CLIENTE`. Nesse cenário, `PEDIDO.id_cliente` é:

- A. necessariamente uma chave primária de PEDIDO.
- B. uma chave estrangeira, que pode se repetir em vários pedidos.
- C. um domínio que define todos os valores permitidos para CLIENTE.
- D. uma chave candidata de CLIENTE por definição.

### Questão 3

Uma inserção em `PEDIDO` informa um `id_cliente` que não existe em `CLIENTE`, e a regra de integridade referencial não permite essa referência. Qual restrição é violada?

- A. Integridade de domínio.
- B. Integridade referencial.
- C. Integridade de entidade.
- D. Independência lógica.

## 11. Registro e continuidade

- [ ] Anotar o tempo efetivamente dedicado a esta parte da sessão.
- [ ] Responder às três questões e registrar o resultado após a correção.
- [ ] Próximo passo sugerido: praticar consultas SQL básicas e aprofundar relacionamentos e normalização gradualmente.
