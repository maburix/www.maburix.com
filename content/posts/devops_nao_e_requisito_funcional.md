---
title: "DevOps não é Requisito Funcional e nem Requisito Não Funcional"
date: 2019-05-13T14:45:30-03:00
draft: false
toc: false
images:
tags: 
  - devops
---
![](/images/aaron-burden-680463-unsplash.jpg)

Esta é uma das perguntas recorrentes que nos fazem, este é um ensaio sobre DevOps e requisitos funcionais e não-funcionais. Mas antes de tudo, vamos primeiramente definir o que é Requisito Funcional:

*"Os requisitos funcionais são características que um software deve ter para atender ao que usuário precisa para realizar sua tarefa ou trabalho"*

O [MITRE]() é famoso pela base dados sobre vulnerabilidade de diversos softwares ao longo de muitos anos, contudo eles têm uma documentação muito rica sobre Desenvolvimento de Software, Operação de TI e Segurança. O documento "[The MITRE Systems Engineering Guide](https://www.mitre.org/publications/technical-papers/the-mitre-systems-engineering-guide)" tem uma definição excelente sobre o tema: "*Requisitos funcionais estão associados à capacidade/aplicação necessária para suportar diretamente os usuários na realização das suas missões/tarefas (funcionalidades, componentes, etc.*)".

Definido o que é Requisito Funcional, alguns anos atrás a minha definição sobre DevOps era "*DevOps significa uma cultura para permitir que as organizações (e a TI) alterarem seus processos, transformando-as de organizações de baixa para alta performance*".  Desde então esta definição precisava ser um pouco mais detalhada para - "*DevOps é uma mudança cultural na cultura de TI com foco ega rápida de serviços aplicando práticas de Agile, Lean, SRE e Safety Culture orientado a propósito do **negócio**. Ele é implementado através de ferramentas que automatizam processos, possibilitando a experimentação, a aprendizagem com foco nas pessoas e cultura.*"

Observando as definições sobre DevOps e Requisitos Funcionais não há uma relação direta entre eles, certo?  realmente não há. Ainda que fosse realizado um esforço de simplificação do termo um esforço de simplificação hipotética do significado do termo DevOps para somente ser uma ferramenta de **Continuous Delivery** (Entrega Contínua), orquestração de nuvem ou monitoramento aplicando conceitos de [Observability](https://thenewstack.io/monitoring-and-observability-whats-the-difference-and-why-does-it-matter/) não poderia ser considerado qualquer uma destas derramentas ou melhor, os serviços providos por elas como requisito funcional porque nenhuma delas representam diretamente a entrega de funcionalidades para o usuário/cliente.

Isso pode parecer um pouco estranho porque poderia argumentar que o todas elas ajudam entregar um melhor serviço, resiliência e disponibilidade. Contudo, nenhum deles está relacionado de fato com entrega de fato, porque eles dão o suporte o que se entrega ao usuário/cliente. Ou seja, eles estão indiretamente relacionado as funcionalidades que serão entregues aos usuários/clientes. Exceto se eles forem o escopo da entrega.

**DevOps não pode ser considerado como Requisito funcional, mas poderia ser considerado como Requisito Não Funcional?**

Recorrendo novamente ao "The MITRE System Engineering Guide", ele define Requisito Não Funcional como - "*... é um requisito que com critérios específicos can pode ser usado para julgar a operação de um sistema, ao invés de comportamentos específicos. Pode se tratar de uma propriedade que o produto final deve ter, padrões pelos quais devem ser criados ou o ambiente que deve existir. Exemplos são usabilidade, facilidade de manutenção, extensibilidade, escalabilidade, reusabilidade, segurança e portabilidade*".

Considerando a definição no início do texto sobre DevOps, ele também não poderia ser definido como Requisito Não Funcional, isso porque ele está relacionado a mudança cultural. Se levarmos em consideração que algumas organizações consideram DevOps como uma função de trabalho (exemplo: DevOps Engineering), torna-se um pouco estranho porque DevOps deixaria de ser um requisito funcional e/ou não funcional para se tornar um usuário/cliente que solicita funcionalidades funcionais e não funcionais. Equipes ou funções de trabalho que são consideradas DevOps são disfuncionais do ponto de vista da organização mas este tema sobre equipes será melhor discutido em outro texto.

Contudo, há uma maneira de ver DevOps como parte indireta das entregas como parte de Requisitos Não Funcionais quando aplicado a ferramentas/serviços ou arquitetura de sistema. Exemplo:

`Uma aplicação de autorização de compra de um E-Commerce deve ser resiliente, ter a maior disponibilidade possível e desempenho para suportar picos de tráfego como Black Friday e campanhas promocionais. Uma das abordagens para entregar seria usar Orquestradores de containers como Kubernetes instalado em diferentes datacenters, ou melhor, em diferentes regiões de disponibilidade se o E-Commerce estiver num IaaS, o site também deverá adotar arquitetura de Micro Serviços, criptografia end-to-end, etc.`

Considerando que foi estipulado o SLA de disponibilidade é de **99,9%** e o SLO é de **500 milisegundos** por autorização de compra. Esta aplicação somente poderá fazer deploys se tiver testando num ambiente de homologação, passado por todos os **Testes Unitários, de sistema**, **integração**. Também passado pelos testes de **Análise Estática**, **Qualidade de Código com score acima de 80%**. O deploy deverá ocorrer no [Kubernetes](https://kubernetes.io/) porque a aplicação está sendo desenvolvida em containers, deverá ter usar um **Side Car** para cada Micro Serviço porque estará rodando numa rede [Service Mesh](https://istio.io/docs/concepts/what-is-istio/#what-is-a-service-mesh).

Cada **Micro Serviço** deverá ter ao menos duas instâncias em cada região de disponibilidade do **provedor de nuvem** (IaaS) e **healthcheck**. Cada Micro-Serviço deverá diferentes níveis de logs e os mesmos deverão ser enviados para um serviço de **Correlacionamento de Eventos**, como também, para de monitoramento. Não poderá esquecer de implementar em cada Micro Serviço a biblioteca do **Serviço de Profiler** usado pela organização para aplicar os conceitos de Observability.

Os Requisitos Não Funcionais solicitados pelo E-Commerce estão diretamente relacionado à várias ferramentas, serviços e conceitos que tornaram-se populares com DevOps. Apesar dele não ser considerado diretamente como parte de Requisitos Funcionais e Não Funcionais, DevOps influenciam diretamente a entrega deles para os usuários/clientes com potencial de maior qualidade, resiliência, disponibilidade e segurança usando diversas ferramentas, métodos e técnicas relacionadas a DevOps.

Comentem. :)
