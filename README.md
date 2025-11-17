# T1---Implementa-o-de-Padr-o-de-Projeto
Disciplina de Arquitetura de Software - UFR

Implementação do Padrão de Projeto Strategy

Este repositório contém a implementação do padrão de projeto **Strategy** (Estratégia) utilizando a linguagem TypeScript. O projeto exemplifica um cenário de sistema de vendas onde o cálculo de frete pode variar dinamicamente sem alterar a estrutura principal do pedido.

Descrição da Implementação

O padrão escolhido foi o Strategy, classificado como um padrão comportamental que "define uma família de algoritmos, encapsula cada um deles e os torna intercambiáveis".

Neste exemplo, implementamos um sistema de cálculo de fretes onde:
1.  **Interface Comum (`FreteStrategy`):** Define o contrato que todas as estratégias de frete devem seguir.
2.  **Estratégias Concretas:** Classes separadas para cada regra de negócio (`FreteComum`, `FreteExpresso`, `FreteGratis`).
3.  **Contexto (`Pedido`):** A classe principal que delega a responsabilidade do cálculo para a estratégia configurada, permitindo a troca do algoritmo em tempo de execução.

Uso na Arquitetura de Software

Na arquitetura de software, utilizamos o padrão Strategy para promover o desacoplamento entre a regra de negócio e o consumidor dessa regra.

Em vez de ter uma classe `Pedido` monolítica contendo múltiplos blocos de `if/else` ou `switch` para verificar o tipo de frete, a arquitetura delega essa responsabilidade. Isso permite que o sistema siga o princípio "Aberto/Fechado" (Open/Closed Principle), onde a arquitetura está aberta para extensão (novos tipos de frete) mas fechada para modificação (não é necessário alterar a classe `Pedido` para adicionar uma nova regra).

Benefícios do Padrão

A utilização deste padrão traz os seguintes benefícios arquiteturais:

Eliminação de Condicionais Complexas:** Remove a necessidade de longas cadeias de verificação de tipos dentro da classe principal.
Manutenibilidade e Coesão:** Cada regra de cálculo fica isolada em sua própria classe. Se a regra do "Frete Expresso" mudar, altera-se apenas a classe `FreteExpresso`, sem risco de quebrar o "Frete Comum".
Intercambialidade:** Permite que o comportamento do software seja alterado dinamicamente durante a execução (runtime) apenas trocando o objeto da estratégia.
Testabilidade:** Torna mais fácil testar cada estratégia de frete isoladamente.

Instalação e Execução

Siga os passos abaixo para rodar o projeto em sua máquina:

Pré-requisitos
* Node.js instalado.
