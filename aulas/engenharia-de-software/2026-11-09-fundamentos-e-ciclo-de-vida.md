# Aula — Fundamentos de Engenharia de Software e ciclo de vida

- **Disciplina:** Engenharia de Software
- **Data de preparação:** 2026-11-08
- **Data da sessão:** 2026-11-09
- **Duração prevista:** 45 minutos
- **Tema:** Conceito de Engenharia de Software, ciclo de vida, requisitos e processos de desenvolvimento
- **Status:** Conteúdo ministrado; 45 minutos registrados; questões respondidas e corrigidas.

## 1. Objetivos

Ao final desta parte da sessão, você deverá conseguir:

1. Explicar por que Engenharia de Software envolve mais do que programar.
2. Reconhecer atividades comuns do ciclo de vida de um software.
3. Distinguir requisito funcional de requisito não funcional.
4. Comparar, em nível introdutório, processos sequenciais, incrementais e iterativos.

## 2. Pré-requisitos

- Nenhum conhecimento teórico prévio é necessário.
- Sua experiência profissional com desenvolvimento será útil para relacionar os conceitos a situações reais; nesta aula, o foco é organizar a terminologia comum em provas.

## 3. Roteiro — 45 minutos

| Etapa | Tempo |
|---|---:|
| Objetivos e conexão com a experiência prática | 3 min |
| O que é Engenharia de Software | 7 min |
| Ciclo de vida e atividades | 10 min |
| Requisitos funcionais e não funcionais | 9 min |
| Processos sequenciais, incrementais e iterativos | 8 min |
| Questões e revisão | 8 min |
| **Total** | **45 min** |

## 4. Engenharia de Software: mais do que escrever código

Desenvolver um programa é parte do trabalho, mas um sistema útil também precisa atender a necessidades reais, funcionar de modo confiável, ser compreensível por quem o mantém e evoluir quando os requisitos mudam.

Em termos didáticos, **Engenharia de Software** é a aplicação sistemática de conhecimentos, métodos e práticas para especificar, projetar, construir, testar, entregar e manter software.

Pense na construção de uma ponte. Não basta montar peças: é preciso entender o uso esperado, planejar, escolher materiais, construir, inspecionar e cuidar da estrutura ao longo do tempo. No software, código é essencial, mas é apenas uma parte do produto e do processo.

Entre os artefatos e resultados de um trabalho de software podem estar:

- programas e componentes;
- dados e configurações;
- documentação técnica e de uso;
- testes e evidências de qualidade;
- procedimentos de implantação e operação.

O peso de cada item varia conforme o produto e o contexto. A ideia central é que o trabalho precisa ser planejado e controlado, não apenas “codificado”.

## 5. Ciclo de vida do software

O **ciclo de vida** representa atividades realizadas desde a identificação da necessidade até a operação e evolução do software. Uma visão inicial inclui:

1. **Planejamento e viabilidade:** compreender o problema, objetivos, restrições, custos, riscos e alternativas.
2. **Requisitos:** descobrir e registrar o que as pessoas usuárias e o negócio precisam.
3. **Análise e projeto:** definir como o sistema será organizado e como seus componentes atenderão aos requisitos.
4. **Implementação:** construir o software.
5. **Verificação e validação:** avaliar se o produto foi construído corretamente e se atende à necessidade pretendida.
6. **Implantação e operação:** disponibilizar o software e acompanhá-lo em uso.
7. **Manutenção e evolução:** corrigir defeitos, adaptar o software e implementar melhorias.

Essas atividades não precisam ocorrer uma única vez nem sempre na mesma ordem. Em um processo iterativo, por exemplo, parte dos requisitos, do projeto, da implementação e dos testes pode se repetir em ciclos.

### Verificação e validação — distinção inicial

- **Verificação:** “Estamos construindo o produto de acordo com o que foi especificado?”
- **Validação:** “Estamos construindo o produto adequado à necessidade de quem vai usá-lo?”

Uma equipe pode implementar corretamente uma especificação e, ainda assim, descobrir que a especificação não resolveu o problema real. Por isso, as duas perguntas são importantes.

## 6. Requisitos

Um **requisito** descreve uma necessidade, condição ou capacidade esperada do sistema.

### Requisito funcional

Descreve **uma função ou comportamento** que o sistema deve oferecer.

Exemplos:

- permitir que uma pessoa usuária consulte o andamento de um processo;
- calcular o total de uma solicitação;
- emitir um relatório de atendimentos por período.

### Requisito não funcional

Descreve uma **característica de qualidade, restrição ou condição de operação** do sistema.

Exemplos:

- a consulta deve responder em até dois segundos para determinada carga;
- o sistema deve controlar o acesso de acordo com o perfil da pessoa usuária;
- a interface deve funcionar em navegadores definidos pelo órgão.

**Dica para classificar:** se a frase descreve uma ação que o sistema oferece, tende a ser funcional. Se estabelece uma qualidade, limite ou restrição para essa função, tende a ser não funcional.

“O sistema deve ser rápido” é pouco verificável. Um requisito fica mais útil quando é mensurável e contextualizado, por exemplo: “95% das consultas devem responder em até dois segundos, sob uma carga de até 500 solicitações simultâneas”.

## 7. Processos de desenvolvimento: primeiras distinções

Um **processo de desenvolvimento** organiza as atividades e a forma como elas são realizadas. Há diferentes modelos e práticas; nenhum processo é automaticamente adequado a todo projeto.

### Processo sequencial

As fases são organizadas predominantemente em sequência. Uma etapa costuma ser concluída antes de avançar para a seguinte.

- Pode facilitar planejamento e documentação quando o escopo é relativamente estável.
- Mudanças tardias podem exigir retrabalho, sobretudo se decisões anteriores já estiverem consolidadas.

### Processo incremental

O produto é entregue em partes funcionais chamadas **incrementos**. Cada incremento acrescenta capacidades ao que já foi entregue.

**Exemplo:** primeiro liberar consulta de processos; depois, incluir notificações; em seguida, acrescentar relatórios.

### Processo iterativo

O produto é revisto e refinado por ciclos. Uma versão inicial pode ser avaliada, receber feedback e ser melhorada.

Incremental e iterativo não são sinônimos: o incremental enfatiza **acrescentar partes funcionais**; o iterativo enfatiza **revisar e aperfeiçoar**. Um mesmo processo pode combinar os dois.

Métodos ágeis valorizam ciclos curtos, colaboração e resposta a mudanças, mas “ágil” não significa ausência de planejamento, documentação ou controle. Essas práticas são ajustadas ao contexto.

## 8. Resumo essencial

- Engenharia de Software organiza o trabalho para produzir e manter software; não se limita à programação.
- O ciclo de vida inclui atividades como requisitos, projeto, implementação, testes, implantação e manutenção.
- Verificação pergunta se o produto está de acordo com a especificação; validação pergunta se ele atende à necessidade.
- Requisitos funcionais descrevem comportamentos; não funcionais descrevem qualidades, restrições ou condições.
- Incremental significa adicionar capacidades em partes; iterativo significa revisar e refinar em ciclos. Processos podem combinar ambos.

## 9. Questões de fixação

Questões autorais para treinamento, não atribuídas a banca ou prova específica. Responda antes de consultar materiais externos; o gabarito será comentado após sua tentativa.

### Questão 1

Uma equipe confirma que uma funcionalidade foi implementada conforme a especificação aprovada. Essa atividade está mais diretamente relacionada a:

- A. Validação, pois confirma que a solução atende à necessidade do usuário.
- B. Verificação, pois compara o produto com o que foi especificado.
- C. Manutenção, pois corrige uma falha depois da implantação.
- D. Estudo de viabilidade, pois escolhe entre alternativas de negócio.

### Questão 2

Considere os requisitos:

- I. O sistema deve permitir emitir certidões.
- II. 95% das solicitações devem ser processadas em até três segundos, sob carga definida.

A classificação mais adequada é:

- A. I e II são funcionais.
- B. I é não funcional e II é funcional.
- C. I é funcional e II é não funcional.
- D. I e II são não funcionais.

### Questão 3

Em um projeto, cada versão acrescenta novas capacidades ao sistema; depois, as equipes também revisam funcionalidades existentes com base no retorno das pessoas usuárias. Essa descrição:

- A. combina desenvolvimento incremental e iterativo.
- B. descreve exclusivamente um processo sequencial.
- C. mostra que o projeto não possui ciclo de vida.
- D. caracteriza manutenção corretiva, necessariamente.

## 10. Registro e continuidade

- [x] Anotar o tempo efetivamente dedicado a esta parte da sessão: 45 minutos, registrados na planilha.
- [x] Responder às três questões e registrar o resultado após a correção.
- [ ] Próximo passo sugerido: aprofundar requisitos, casos de uso e modelagem, conforme a evolução da turma.
