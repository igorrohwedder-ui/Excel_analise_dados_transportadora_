# Excel_analise_dados_transportadora
Realizei um projeto de análise de dados no Excel usando uma base fictícia. Fiz o ETL, tratei e uni diferentes bases em uma planilha única com fórmulas avançadas. A partir disso, criei tabelas dinâmicas, identifiquei insights relevantes e desenvolvi gráficos e um PowerPoint para apresentar os resultados.

Para este projeto, utilizei a base Brazilian E-Commerce Public Dataset by Olist, disponível no Kaggle.
Link da base: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

Realizei o download dos arquivos em formato CSV, contendo informações de pedidos, produtos, pagamentos, clientes e logística. Em seguida, importei esses dados no Excel para iniciar o processo de ETL, focando especialmente na parte logística da operação.

<img width="1427" height="688" alt="image" src="https://github.com/user-attachments/assets/7a485b6b-66a5-4245-9642-cba17274bc16" />

Para tornar a base utilizável no Excel, primeiro converti a coluna de estimativa de entrega para um formato de data sem horário, garantindo padronização para análises. Em seguida, ordenei os IDs dos pedidos do menor para o maior e selecionei apenas os 10 mil primeiros registros. Essa redução foi necessária porque trabalhar com mais de 100 mil linhas no Excel comprometeria o desempenho e inviabilizaria o processo de análise.

Após preparar a base principal de pedidos, importei também os dados de order_items, que trazem informações essenciais como valor bruto do pedido (price) e valor do frete (freight_value).

<img width="1434" height="773" alt="image" src="https://github.com/user-attachments/assets/62e17712-3f01-428d-aae0-d76701ea362f" />

Ao carregar o CSV no Excel, os valores vieram no padrão americano, utilizando ponto ao invés de vírgula. Por isso, foi necessário converter as colunas de preço e frete para o formato numérico correto, garantindo que o Excel reconhecesse os dados para cálculo.

<img width="687" height="332" alt="image" src="https://github.com/user-attachments/assets/9cae87d2-5c2b-46cb-b35f-d41cc9ee7a0c" />

Após padronizar os valores, ordenei novamente os 10 mil primeiros registros e excluí o restante para possibilitar uma análise eficiente dentro do Excel. (O objetivo deste projeto é me desafiar utilizando apenas Excel, embora o ideal para manipular grandes volumes de dados seria usar SQL ou Python.)

Com os dados reduzidos e padronizados, utilizei a função XLOOKUP para transportar as colunas de preço e frete diretamente para a planilha principal de pedidos, consolidando todas as informações necessárias para iniciar as análises logísticas.

Em seguida, converti a base em Tabela Dinâmica, onde realizei as primeiras análises, como:

Taxa de cancelamento × taxa de pedidos entregues

<img width="344" height="63" alt="image" src="https://github.com/user-attachments/assets/f27e6404-737d-4386-96e7-1c9ec89f946f" />

Valor do frete × taxa de cancelamentos

<img width="350" height="60" alt="image" src="https://github.com/user-attachments/assets/32fa73ed-c737-4d0c-a637-0c967f163df4" />

Já nessas primeiras explorações, identifiquei um ponto importante: embora a taxa de cancelamento seja baixa (0,76%), o frete dos pedidos cancelados é aproximadamente 74% mais caro que o dos pedidos entregues, indicando uma possível sensibilidade do cliente ao preço do frete.
Sempre que encontro uma análise relevante e com potencial de gerar insight, copio os resultados para uma aba de resumo, que utilizo para selecionar as informações mais importantes (ou aquelas que seriam de maior interesse para um gestor) ao final do processo.

Depois disso, importei também a base de pagamentos, com o objetivo de analisar formas de pagamento, valores médios, número de parcelas e o valor total do pedido. Assim como nas outras bases, precisei converter novamente os valores para o formato decimal americano, evitando erros de cálculo no Excel.

Com os dados padronizados, utilizei XLOOKUP para trazer para a planilha principal as informações de tipo de pagamento, quantidade de parcelas e valor total pago (valor bruto + frete).

Após consolidar tudo em uma única planilha, voltei para a tabela dinâmica para realizar novas análises e extrair insights relacionados ao comportamento de pagamento dos clientes.

Observei a media de pagamentos em relaçao ao status do pedido 

<img width="347" height="132" alt="image" src="https://github.com/user-attachments/assets/ff420474-9db6-4264-8d5d-0f734b60bb34" />

Percebi que pedidos cancelados possuem o maior valor médio (R$ 259), confirmando que tickets altos apresentam maior risco de desistência. Já os pedidos entregues têm o menor valor médio (R$ 156), indicando que valores mais baixos convertem com maior facilidade. Isso evidencia uma sensibilidade ao preço: pedidos mais caros tendem a enfrentar mais resistência durante o processo de compra.

Após isso, analisei o comportamento de pagamento dos clientes. As informações avaliadas foram o tipo de pagamento em relação à quantidade percentual de uso e a média de preço por tipo de pagamento.

<img width="349" height="100" alt="image" src="https://github.com/user-attachments/assets/175a789c-62ee-4709-858b-9bba2c7ba2d7" />
<img width="343" height="95" alt="image" src="https://github.com/user-attachments/assets/1dea833e-efc5-4a59-a3c0-b73f94f02272" />

Pude observar que o cartão de crédito representa 75,8% das transações e possui o maior ticket médio (R$ 132,06), sendo o principal impulsionador de receita da operação. O boleto corresponde a 20,09% das transações e apresenta um ticket médio intermediário (R$ 105,30), indicando um perfil de cliente mais sensível ao preço, mas ainda relevante para o volume total de pedidos. Métodos como cartão de débito (1,41%) e voucher (2,69%) mostram baixa adesão e apresentam tickets médios menores (R$ 94,84 e R$ 81,89), evidenciando impacto operacional e financeiro limitado dentro da operação.

E por ultimo realizei uma analise de Relação entre Tipo de Pagamento e Tipo de Pedido.

<img width="815" height="104" alt="image" src="https://github.com/user-attachments/assets/ac26f7fb-676b-4a08-a305-e7b367ec40b5" />

Percebi que seria melhor transformar os dados obtidas nessa tabela em um grafico de calor para mais facil discernimento

<img width="984" height="109" alt="image" src="https://github.com/user-attachments/assets/89212d6a-64ea-4c12-9ea0-84a01ade9458" />

Entao conclui que : O cartão de crédito se destaca por sua estabilidade operacional, apresentando apenas 0,66% de cancelamentos e uma taxa de entrega de 97,82%, o que indica que é o método mais confiável dentro do fluxo de pedidos. O voucher, por outro lado, demonstra fragilidade, com 5,11% de cancelamentos e 93,19% de entregas, sendo o método que mais perde pedidos ao longo do processo, sinalizando a necessidade de revisão e otimização. O cartão de débito não registra cancelamentos, mas concentra 0,81% dos pedidos no status “Faturado”, o que sugere possíveis atrasos nessa etapa e dificulta o avanço eficiente dos pedidos.

Após consolidar as informações, criei uma nova planilha chamada “Gráficos”, onde utilizei os resultados da tabela dinâmica da planilha “Resumo” para gerar os gráficos correspondentes.
Esses gráficos serão apresentados em um PowerPoint, acompanhados dos insights obtidos a partir dos dados. Ao final da apresentação, serão destacadas conclusões, observações e sugestões de melhoria nos processos, com base nas análises realizadas.

Deixarei este PowerPoint disponível para download e visualização. Fique à vontade para explorá-lo, observar os gráficos e analisar os insights apresentados.

Conclusão do Projeto

Este primeiro projeto de análise de dados permitiu compreender e aplicar na prática conceitos de organização, filtragem e visualização de informações utilizando apenas Excel e PowerPoint. A partir das tabelas dinâmicas e gráficos elaborados, foi possível identificar padrões, pontos fortes e oportunidades de melhoria nos processos analisados.

Além de reforçar o domínio das ferramentas, o projeto evidenciou a importância de transformar dados em insights claros e acionáveis, permitindo tomadas de decisão mais embasadas. Com essa experiência, foi possível perceber como análises estruturadas podem orientar melhorias operacionais, mesmo com ferramentas básicas, e servirá como base sólida para projetos futuros mais complexos.
