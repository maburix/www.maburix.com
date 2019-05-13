---
title: "DevOps não é requisito funcional"
date: 2019-05-10T16:44:30-03:00
draft: true
toc: false
images:
tags: 
  - devops
---
Antes de tentar responder a pergunta do título, vamos primeiramente definir o que é Requisito Funcional:

*"Os requisitos funcionais são características que um software deve ter para atender ao que usuário precisa para realizar sua tarefa ou trabalho"*

Uma definição um pouco mais abrangente sobre o tema  usemos a definição do MITRE sobre o tema: "Requisitos funcionais estão associados à capacidade/aplicação necessária para suportar diretamente os usuários na realização das suas missões/tarefas (funcionalidades, componentes, etc.) - 
"[The MITRE Systems Engineering Guide](https://www.mitre.org/publications/technical-papers/the-mitre-systems-engineering-guide)".

Definido o que é Requisito Funcional, o que é DevOps? 

DevOps é uma mudança cultural na cultura de TI com foco ega rápida de serviços aplicando práticas de Agile, Lean, SRE e Safety Culture orientado a propósito do **negócio**. Ele é implementado através de ferramentas que automatizam processos, possibilitando a experimentação, a aprendizagem com foco nas pessoas e cultura. 

Olhando as definições acima, DevOps não encaixa com requisito funcional. Mesmo num esforço de simplificação afirmando hipoteticamente que DevOps seria uma ferramenta de Continuous Delivery (Entrega Contínua), ferramenta de provisionamento de nuvem ou ferramenta de monitoramento aplicando os conceitos de Observability, não poderia ser considerado como requisito funcional porque nenhuma delas representa a entrega de funcionalidade para o usuário/cliente.

DevOps pode ser considerado como requisito não funcional?

Como exercitado acima, vamos a definição usada pelo MITRE:

"Requisito não funcional é um requisito que com critérios específicos can pode ser usado para julgar a operação de um sistema, ao invés de comportamentos específicos. Pode se tratar de uma propriedade que o produto final deve ter, padrões pelos quais devem ser criados ou o ambiente que deve existir. Exemplos são usabilidade, facilidade de manutenção, extensibilidade, escalabilidade, reusabilidade, segurança e portabilidade."

DevOps também não é requisito não funcional porque está relacionado a mudança cultural, algumas organizações definem como equipe chamando de DevOps Engineers, tornando DevOps ainda mais difícil de ser aplicado como requisito funcional ou não funcional. Porém, as ferramentas e conceitos aplicados para aplicá-lo podem fazer parte das entregas relacionadas à requisitos não funcional. 

Uma aplicação de autorização de compra de um E-Commerce, ela deve ser resiliente, ter a maior disponibilidade possível e desempenho para suportar picos de tráfego como Black Friday e campanhas promocionais. Algumas maneiras de entregar resiliência, disponibilidade e desempenho são via Orquestradores de containers que irão suportar as aplicações usando diferentes datacenter (regiões de disponibilidade no caso de IaaS), Arquitetura de Micro Serviços, criptografia TLS end-to-end, etc. 

Imaginando que a organização estipulou que o SLA de disponibilidade é de 99,9% e o SLO é de 500 milisegundos por autorização de compra, esta aplicação somente poderá fazer deploys se tiver testando num ambiente de homologação, passado por todos os testes unitários, de sistema, integração. Também passado pelos testes de análise estática, qualidade de código. O deploy deverá ocorrer em um orquestrador de container mais usado do mercado, sendo ele implementado ao menos duas regiões de disponibilidade do provedor de nuvem, a aplicação deverá ter healthcheck e será realizado deploy com no mínimo 4 instâncias, duas em cada região de disponibilidade. A aplicação deverá ter níveis de logs diferenciados, sendo que os logs serão enviados para um serviço de monitoramento, portanto, a aplicação deverá usar um serviço de profiler para fazer correlação de eventos em conjunto com o correlacionado de eventos (Observability). 

Apesar dos requisitos não funcionais descrito acima serem um pouco genérico, mas os requisitos não funcionais mencionados acima fazem parte de diversas implementações de DevOps no mundo. DevOps não pode ser considerado como parte de uma especificação de requisitos não funcionais, mas ele é indiretamente implementado ao usar métricas, serviços e ferramentas conhecidas por serem parte ou influenciado por DevOps.