# Estudo de Caso -- Arquitetura Wi-Fi Industrial (Estaleiro)

## Visão Geral

Este repositório documenta um **estudo de caso técnico** de projeto e
implantação de uma infraestrutura Wi‑Fi para um ambiente industrial do
tipo estaleiro, caracterizado por severos desafios de radiofrequência
(RF).

O objetivo principal do projeto foi construir uma rede sem fio
**estável, previsível e escalável**, priorizando qualidade de serviço,
continuidade de conexão e confiabilidade operacional, em vez de apenas
altas velocidades nominais.

Todas as informações sensíveis (nomes reais, senhas, SSIDs,
endereçamento IP e dados corporativos) foram propositalmente removidas
ou anonimizadas.

Equipamento: Antenas Ubiquiti\
Controladora Network da Ubiquiti

------------------------------------------------------------------------

## Características do Ambiente

-   Estruturas antigas com concreto armado espesso
-   Grande presença de ferro e estruturas metálicas
-   Máquinas em operação contínua
-   Empilhamento dinâmico de materiais
-   Alta densidade de usuários e dispositivos
-   Convivência entre dispositivos modernos e legados

------------------------------------------------------------------------

## Link de Internet

-   Download: 500 Mbps
-   Upload: 400 Mbps

O projeto considera **traffic shaping e QoS obrigatórios**, com foco
especial na proteção do upload, visando preservar aplicações sensíveis à
latência.

------------------------------------------------------------------------

## Segmentação da Rede

### Ambiente Administrativo

-   Diretoria 
-   Corporativo
-   Visitante aAdm

### Área Comum / Operacional

-   Sistemas (coletores, totens, impressoras)
-   Clientes
-   Visitante OP

Cada SSID possui: - Perfil próprio de controle de banda - Prioridade de
tráfego - Políticas de segurança e isolamento adequadas ao uso

------------------------------------------------------------------------

## Estratégia de Controle de Banda (Exemplo)

  | Perfil | Download | Upload |
  |--------|----------|--------|
  Diretoria |         200 Mbps |  60 Mbps
  Corporativo |       180 Mbps |  50 Mbps
  Visitante Adm |  40 Mbps |   10 Mbps
  Sistemas |          100 Mbps |  40 Mbps
  Clientes |          120 Mbps |  50 Mbps
  Visitante OP |   25 Mbps |   5 Mbps

A proteção do **upload** foi considerada crítica para garantir
estabilidade geral da rede.

------------------------------------------------------------------------

## Princípios de Projeto de Rádio

### Banda 2.4 GHz

-   Canais: 1 / 6 / 11
-   Largura: 20 MHz
-   Potência: Média
-   RSSI ajustado para compatibilidade com dispositivos legados

### Banda 5 GHz

-   Largura: 40 MHz
-   Potência controlada conforme ambiente
-   Canais manuais em áreas industriais
-   Roaming otimizado apenas no ambiente administrativo

A estratégia adotada prioriza **mais pontos de acesso com células
menores**, em vez de alta potência de transmissão.

------------------------------------------------------------------------

## Decisões Técnicas Relevantes

-   Qualidade de serviço (QoS) acima de velocidade máxima
-   Previsibilidade acima de throughput de pico
-   Proteção rigorosa de upload
-   Roaming limitado em áreas industriais
-   Uso de mesh apenas como contingência
-   Compatibilidade com dispositivos legados

------------------------------------------------------------------------

## Resultados Observados

-   Conectividade estável em ambiente RF hostil
-   Melhoria significativa em videoconferências
-   Redução de problemas de roaming
-   Diminuição de chamados relacionados a Wi‑Fi
-   Infraestrutura preparada para expansão futura

------------------------------------------------------------------------

## Aviso Legal

Este repositório representa um **estudo de caso técnico** e não expõe
informações confidenciais. Não se trata de um guia completo de
implantação, mas sim de uma documentação conceitual e arquitetural.

------------------------------------------------------------------------

## Autor

Willian Miranda\
Analista de Infraestrutura e Redes\
Estudo de Caso -- Wi‑Fi Industrial
