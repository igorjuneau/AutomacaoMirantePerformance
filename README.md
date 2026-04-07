# 🚀 Projeto de Automação de Performance - BlazeDemo

> [!IMPORTANT]
> ### ⚠️ AVISO DE PROPRIEDADE E ÉTICA PROFISSIONAL
> Este repositório é público exclusivamente para fins de **portfólio e avaliação**. 
> A cópia total ou parcial deste código para uso em desafios ou processos seletivos é **estritamente proibida**. 
> O histórico de commits e originalidade é monitorado. Use este material apenas como referência de estudo.

---
Este repositório contém a automação de testes de performance para o fluxo de compra de passagens 
do site [BlazeDemo](https://www.blazedemo.com). O objetivo é validar a resiliência e o tempo de 
resposta da aplicação sob carga moderada.

## 📋 Critérios de Aceitação (Challenge)

Para a aprovação neste cenário, foram estabelecidos os seguintes SLAs (Service Level Agreements):
* **Vazão (Throughput):** Mínimo de 250 Requisições por Segundo (RPS).
* **Tempo de Resposta:** 90º Percentil (90th percentile) abaixo de 2 segundos.
* **Taxa de Erro:** 0%.

---

## 🛠️ Tecnologias Utilizadas

* **Java 11**: Linguagem base para suporte e logs.
* **Apache JMeter 5.5**: Motor principal de execução dos testes.
* **JMeter Maven Plugin**: Gerenciamento do ciclo de vida do teste e dependências.
* **GitHub Actions**: Pipeline de CI para execução automatizada em cada Push.

---

## 🏗️ Estrutura do Projeto

O projeto segue uma estrutura organizada para facilitar a manutenção:

* `src/test/jmeter/`: Contém o script de performance (`.jmx`).
* `src/test/resources/`: Arquivos de propriedades e massa de dados.
* `src/test/java/.../setup/`: Classes auxiliares para leitura de configurações.
* `.github/workflows/`: Definição do pipeline de integração contínua.

---

## 🚀 Como Executar Localmente

Certifique-se de ter o **Maven** instalado e configurado no seu PATH.

1. Clone o repositório.
2. No terminal, execute o comando:
   ```bash
   mvn clean verify
Após a execução, o relatório HTML detalhado estará disponível em:target/jmeter/reports/
BlazeDemo_Performance/index.html📊 Resultados ObtidosApós a execução do cenário de carga com 100
usuários simultâneos (Threads) e um ramp-up de 60 segundos, obtivemos os seguintes resultados:
MétricaMeta (SLA)ResultadoStatusVazão250 RPS254.1 RPS✅ Sucesso90th Percentile< 2.0s1.21s✅ 
SucessoTaxa de Erro0.00%0.00%✅ SucessoAnálise Técnica:A aplicação BlazeDemo demonstrou 
estabilidade durante o teste de 5 minutos. O tempo de resposta médio manteve-se constante, 
e o 90th percentile de 1.21s confirma que 90% dos usuários tiveram uma experiência de navegação 
rápida, bem abaixo do limite crítico de 2 segundos.🤖 CI/CD (GitHub Actions)Este projeto conta 
com um workflow automatizado que executa os testes de performance a cada commit.O artefato do 
relatório (JMeter Report) é gerado e fica disponível para download na aba Actions do repositório 
por 5 dias.
