## MÉTODOS FORMAIS

Prof. Júlio Machado

## INTRODUÇÃO

Conceitos Fundamentais

## Software e qualidade

- Software é um dos mais variados e complexos produtos produzidos de forma regular.
- Requisitos de qualidade dependentes:
- Do domínio da aplicação
- Ambiente de execução
- Público alvo
- Etc.
- Exige técnicas sofisticadas e específica para cada produto desenvolvido.

## Software e qualidade

## · Ariane 5:

- Explosão em seu primeiro voo.
- Causado pelo reuso de algumas partes de código de seu predecessor sem verificação adequada.

## · Therac-25:

- Máquina de terapia de radiação.
- Devido a um erro de software, seis pessoas morreram de overdose.

## · Pentium FDIV:

- Erro de projeto na unidade de divisão de ponto-flutuante.
- Intel foi forçada a oferecer substituição de todos os processadores defeituosos.

![Image](content/images/introducao-artifacts-image_000000_f36317e49c0d791b3f72cfba438d1518bbcc53f83d9e3a750f2a42f001231b4e.png)

## Software e qualidade

- Por que é tão difícil garantir a qualidade do software?
- Porque é algo dinâmico.
- Porque envolve pessoas.
- Porque as regras de negócio podem ser complexas.
- Porque as tecnologias mudam rapidamente.
- Porque as equipes mudam a toda hora.
- Porque novas necessidades surgem a cada momento.

·

...

## Software e qualidade

![Image](content/images/introducao-artifacts-image_000001_f48704bea16df2845a33cecac6829043e4e92812dca05c1424d3bc7d9e291f98.png)

## Verificação

- 'Estamos construindo o produto corretamente?'

![Image](content/images/introducao-artifacts-image_000002_5eca8bff4d1d4c713d0af2e5660f3e0c4be2c6319cebc9fca0a4a769f9f14fb5.png)

![Image](content/images/introducao-artifacts-image_000003_72c5bb53b213a7ac369f3a5641ce754744298b1ee7338d288c899e740b74940a.png)

## Verificação

## O quê é?

- Processo de garantir que o software está sendo construído corretamente
- Foca na conformidade com os requisitos especificados

## Exemplos de técnicas:

- Revisão de Código - Análise estática do código
- Inspeção de Documentação - Revisão de requisitos e especificação
- Análise Estática - Uso de ferramentas para detectar falhas no código sem executá-lo

## Validação

- 'Construímos o produto correto?'

![Image](content/images/introducao-artifacts-image_000004_3991a28f51c774144127c1002eebe5538e5af6f6bcf76d012c8ce25fb851a273.png)

![Image](content/images/introducao-artifacts-image_000005_6532f049ef4ed4f891a08e26ff6cfab3799401253866db7a7ce9dad4cba59b08.png)

## Validação

## O quê é?

- Processo de garantir que o software atende às necessidades do usuário
- Valida se o software está correto para seu uso final

## Exemplos de técnicas:

- Testes de Usabilidade - Mede a experiência do usuário
- Testes de Aceitação - Realizados pelo cliente para verificar se o software atende suas necessidades

## Validação e Verificação

- IMPORTANTE : atividades de verificação e validação apropriadas dependem da disciplina de engenharia, do processo de construção, do produto final e dos requisitos de qualidade.

## Requisitos

- Requisitos funcionais descrevem as funcionalidades que um software deve fornecer.
- Exemplos: formatar um texto, transmitir uma requisição via web .
- Requisitos não-funcionais descrevem restrições que atuam sobre um software; também são conhecidos como requisitos de qualidade.
- Exemplos: o sistema deve transmitir uma requisição via web de forma segura e dentro de um prazo limite.

## Técnicas de V&amp;V

- Agrupamentos de técnicas de validação e verificação:

![Image](content/images/introducao-artifacts-image_000006_0baddb6963422246c369306ded7a4b78ed94739f477b7473326dd94d988f12ba.png)

## Técnicas de V&amp;V

- Técnicas de V&amp;V estáticas não requerem que o sistema de software seja executado.
- Exemplo: revisões manuais de código, análise estática de padrões de código
- Técnicas de V&amp;V dinâmicas requerem trabalhar com uma representação executável do sistema de software.
- Exemplo: teste de software
- Técnicas de V&amp;V formais requerem o uso de linguagens formais de especificação e fundamentos matemáticos sólidos.
- Exemplo: prova de correção

## O que é um Método Formal?

- É (a descrição de) qualquer abordagem que utiliza uma linguagem de especificação formal e ferramentas associadas no processo de desenvolvimento de software.
- Entre essas ferramentas, incluem-se:
- Verificadores de programas
- Verificadores de modelos
- Provadores automático de teoremas
- Assistentes de provas interativos
- Etc.
- Pode significar o uso somente para documentação ou, preferencialmente, também técnicas de verificação e refinamento com automatização.

## O que é uma Linguagem de Especificação Formal?

- Qualquer linguagem na qual é possível especificar completa ou parcialmente a funcionalidade de todo ou parte de um componente de software (ou hardware), e sobre a qual seja possível efetuar algum tipo de raciocínio formal.
- Ela deve possuir uma fundamentação lógico-matemática, em geral na Lógica e na Matemática Discreta.

## Lógicas utilizadas em Métodos Formais

- Lógica de Predicados ou Lógica de Primeira Ordem
- Lógicas de Segunda Ordem (Isabelle, HOL)
- Lógicas de Programas (Lógica de Hoare, Lógica Dinâmica, Lógica de Separação)
- Lógicas Temporais (Lógica de Tempo Linear, Lógica de Tempo Ramificado)
- Lógica Equacional (Especificações Algébricas)

## Porque Métodos Formais?

- Forçam os projetistas/desenvolvedores a pensar cuidadosamente sobre a especificação do sistema, evitando o envolvimento precoce com a codificação.
- Mesmo para aqueles profissionais com uma grande experiência em modelagem/programação, as ideias subjacentes aos métodos formais propiciam uma visão completamente nova sobre sistemas de computação em geral.
- Eles reforçam a ideia de uma abordagem de engenharia para o desenvolvimento de sistemas.
- Eles estão gradualmente sendo implantados em projetos industriais.

## Quando utilizar Métodos Formais?

- Quando for desejável descrever o comportamento de um software/hardware de forma não ambígua.
- Quando algum tipo de argumentação simbólica sobre a correção de um componente de software/hardware for necessária.
- Quando a utilização de métodos formais é entendida como uma das formas de preencher padrão específico.
- Quando o software/hardware for uma aplicação de segurança crítica ou qualquer outra aplicação onde o custo de falhas no sistema seja muito alto.
- Quando a organização já possui um grupo estabelecido com a experiência necessária para utilizar métodos formais.

## VERIFICAÇÃO FORMAL DE SISTEMAS

Introdução

## Verificação Formal

- No contexto de sistemas de software e hardware, verificação formal é o ato de provar ou refutar a correção de um determinado algoritmo , programa ou modelo com relação a uma certa especificação ou propriedade formal , utilizando métodos formais.

## Abordagens para Verificação Formal

- Verificação de Modelos ( Model Checking ):
- Consiste em uma exploração sistemática e exaustiva do modelo matemático (usualmente uma máquina de estados ou uma descrição do sistema em uma linguagem lógica que seja decidível).
- As propriedades a serem verificadas são frequentemente descritas em lógica temporal , como lógica temporal linear (LTL) ou lógica temporal ramificada (CTL) ou em alguma variante da lógica de predicados.
- É baseado em modelos .
- Esta abordagem é suportada por modelos descritos com álgebra de processos ou com uma linguagem subjacente verificadores de modelos (Spin, NuSMV, etc).

## Abordagens para Verificação Formal

## · Verificação Dedutiva:

- Consiste na utilização de uma versão formal de raciocínio matemático (lógico) sobre o sistema de forma a estabelecer propriedades desejadas no sistema.
- As provas são conduzidas dentro de um Cálculo Lógico.
- Normalmente utiliza-se de softwares de apoio como assistentes de prova (Isabelle, Coq, etc) para automatizar certas partes do raciocínio.
- Verificação baseada em inferência (portanto, em provas ).

## Abordagens para Verificação Formal

## · Comparação:

- Na abordagem baseada em provas, a descrição do sistema é um conjunto de fórmulas 𝑆𝑝𝑒𝑐 (em uma determinada lógica) e a especificação é outra fórmula 𝑝𝑟𝑜𝑝 . O método de verificação consiste em tentar achar uma prova de que 𝑆𝑝𝑒𝑐 $\vdash$ 𝑝𝑟𝑜𝑝 ( 𝑝𝑟𝑜𝑝 é um teorema de 𝑆𝑝𝑒𝑐 ).
- Na abordagem baseada em modelos, o sistema é representado por um modelo 𝑀 para uma lógica apropriada. A especificação é novamente representada por uma fórmula 𝑝𝑟𝑜𝑝 e o método de verificação consiste em computar se o modelo 𝑀 satisfaz 𝑝𝑟𝑜𝑝 , isto é, se 𝑀 $\models$ 𝑝𝑟𝑜𝑝 .
