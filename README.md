# Visao-de-tempo-de-negociacao-x-Churn-e-faixa-de-faturamento
Objetivo
Com o objetivo de entender melhor os fatores que influenciam a retenção de clientes, realizamos uma análise de sobrevivência considerando o tempo de negociação — ou seja, o período entre a criação do negócio até o fechamento com pagamento — em conjunto com a faixa de faturamento dos clientes. Utilizamos ferramentas estatísticas como Curvas de Kaplan-Meier e Taxas de Sobrevivência aos 12 meses para investigar como o tempo até o fechamento da venda impacta a probabilidade de churn ao longo do tempo.

Os dados analisados referem-se a todos os clientes com data de fechamento entre 2023 e 21 de abril de 2025.

Análise Descritiva da Base
A tabela a seguir mostra a distribuição de empresas ativas (1) e inativas (0), segmentadas por categorias de tempo de fechamento da venda, com suas respectivas proporções dentro de cada categoria e em relação à base total:

Tempo de fechamento entre 0 e 1 hora representa 23,66% da base.

Clientes sem informação sobre tempo de fechamento somam 25,81%, um reflexo da migração de plataforma do Pipefy para o HubSpot.

| category_time_for_hours | Empresas | Ativo (1=ativo, 0=inativo) | % dentro da categ. | % geral |
|-------------------------|---------|-----------------------------|--------------------|---------|
| Sem informação          | 1012    | 1                           | 33,63%             | 8,68%   |
| Sem informação          | 1997    | 0                           | 66,37%             | 17,13%  |
| 01 - 0 a 1 horas        | 1600    | 1                           | 58,01%             | 13,73%  |
| 01 - 0 a 1 horas        | 1158    | 0                           | 41,99%             | 9,93%   |
| 02 - 1 a 2 horas        | 237     | 1                           | 52,78%             | 2,03%   |
| 02 - 1 a 2 horas        | 212     | 0                           | 47,22%             | 1,82%   |
| 03 - 3 a 6 horas        | 393     | 1                           | 51,85%             | 3,37%   |
| 03 - 3 a 6 horas        | 365     | 0                           | 48,15%             | 3,13%   |
| 04 - 7 a 12 horas       | 144     | 1                           | 47,37%             | 1,24%   |
| 04 - 7 a 12 horas       | 160     | 0                           | 52,63%             | 1,37%   |
| 05 - 13 a 24 horas      | 383     | 1                           | 57,77%             | 3,29%   |
| 05 - 13 a 24 horas      | 280     | 0                           | 42,23%             | 2,40%   |
| 06 - 25 a 48 horas      | 385     | 1                           | 53,92%             | 3,30%   |
| 06 - 25 a 48 horas      | 329     | 0                           | 46,08%             | 2,82%   |
| 07 - 49 a 72 horas      | 244     | 1                           | 57,01%             | 2,09%   |
| 07 - 49 a 72 horas      | 184     | 0                           | 42,99%             | 1,58%   |
| 08 - 73 a 96 horas      | 198     | 1                           | 53,08%             | 1,70%   |
| 08 - 73 a 96 horas      | 175     | 0                           | 46,92%             | 1,50%   |
| 09 - 97 a 120 horas     | 153     | 1                           | 52,76%             | 1,31%   |
| 09 - 97 a 120 horas     | 137     | 0                           | 47,24%             | 1,18%   |
| 10 - 120+ horas         | 1105    | 1                           | 57,85%             | 9,48%   |
| 10 - 120+ horas         | 805     | 0                           | 42,15%             | 6,91%   |
| **TOTAL**               | **10644** |                             |                    |         |

Esses dados ajudam a entender a composição da base e alertam sobre possíveis vieses de informação.

Curva de sobrevivência 
O gráfico abaixo mostra Curvas de Sobrevivência Kaplan-Meier, que representam a probabilidade de retenção dos clientes ao longo do tempo (em meses), de acordo com o tempo de fechamento da venda — ou seja, o intervalo de horas entre a criação do negócio (deal) e o fechamento com pagamento.

Principais insights:
Clientes que fecharam em até 1 hora apresentam queda acentuada na retenção logo nos primeiros meses.

Grupos com fechamento entre 3 a 12 horas apresentam curvas mais estáveis, sugerindo maior retenção.

Ao longo do tempo, as diferenças entre os grupos diminuem, mas os primeiros meses são decisivos para a retenção.

<img width="846" height="548" alt="image" src="https://github.com/user-attachments/assets/258ab127-56f2-4029-8863-b5ed5e55afda" />


Este gráfico sugere que fechar a venda de forma muito acelerada pode estar associado a uma menor retenção de clientes. Isso pode indicar que vendas muito rápidas não dão tempo suficiente para amadurecimento da decisão de compra ou para qualificação adequada do cliente, impactando negativamente sua permanência.

Taxa de Sobrevivência por Faixa de Faturamento e Tempo de Fechamento
O heatmap abaixo apresenta a taxa de sobrevivência após 12 meses, cruzando faixa de faturamento mensal e tempo de fechamento da venda.

Destaques:
Clientes com maior faturamento (acima de R$ 100k) apresentam altas taxas de retenção, especialmente com tempos de fechamento entre 7 e 96 horas.

Faturamentos mais baixos possuem variações mais significativas, com baixa retenção para fechamentos muito rápidos (0–1h).

O tempo de fechamento exerce maior influência entre clientes de menor porte, onde ciclos muito curtos estão associados a churn mais alto.

<img width="1223" height="823" alt="image" src="https://github.com/user-attachments/assets/57de426f-9864-44ad-b2bf-09ed951d64ce" />

Esse heatmap revela que a retenção de clientes após 12 meses depende fortemente do perfil financeiro do cliente (faturamento) e do tempo dedicado à negociação. Ciclos de venda muito rápidos podem prejudicar a retenção, especialmente entre clientes de menor porte. Já ciclos mais moderados (em torno de 3 a 12 horas) parecem ser mais saudáveis para construção de relacionamentos duradouros, especialmente com clientes de maior faturamento.

Correlação do tempo de fechamento com churn
A correlação entre o tempo de fechamento (em segundos) e a variável cliente_ativo é de +0,049, ou seja:

Esse valor é positivo, porém muito fraco.

Isso sugere que quanto maior o tempo de fechamento, ligeiramente maior a probabilidade de o cliente estar ativo, porém essa relação é praticamente nula em termos estatísticos.

Pontos de Atenção
O tempo de negociação foi calculado com base na diferença entre a data de criação do deal e a data de fechamento com pagamento. No entanto, para que essa métrica represente de fato o tempo real de negociação, é fundamental que o deal seja criado no momento do primeiro contato com o cliente.

Durante a validação de alguns casos, foi identificado que a data de criação do deal, em diversas situações, ocorre após a data de criação do contrato financeiro, o que indica que a negociação já estava em andamento antes do registro no CRM. Isso compromete a confiabilidade da variável de tempo de negociação e pode distorcer as conclusões da análise.

Conclusão
Apesar de a análise sugerir que o tempo de negociação e o faturamento do cliente podem influenciar a retenção de longo prazo, a inconsistência dos dados limita a validade dos resultados.

Foi identificado que, em muitos casos, o deal não foi criado no início real da negociação, o que distorce o cálculo do tempo de fechamento.

A baixa correlação estatística (+0,049) entre o tempo de fechamento e a retenção também reforça a fragilidade dessa variável como preditora isolada de churn.

Dessa forma, não é possível afirmar com confiança que o tempo de negociação, da forma como foi calculado, é um fator determinante para retenção. Recomenda-se revisar e padronizar os processos de registro no CRM, garantindo que o deal seja criado no primeiro contato com o cliente. Apenas com dados consistentes será possível gerar insights mais confiáveis e acionáveis para decisões estratégicas
