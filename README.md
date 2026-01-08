# 📊 Excel Análise de Dados — Transportadora  
Projeto completo de análise de dados utilizando **Excel** para ETL, tratamento de dados, criação de indicadores e construção de apresentação final no **PowerPoint**.

---

## 📁 Sobre o Projeto

Este projeto foi desenvolvido com o objetivo de praticar habilidades de **análise de dados utilizando apenas Excel e PowerPoint**, desde o ETL até a apresentação dos insights.  
Para isso, utilizei uma parte da base **Brazilian E-Commerce Public Dataset by Olist**, disponível no Kaggle:

🔗 **Fonte do Dataset:**  
https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

A análise teve foco principalmente na **área logística**, investigando comportamento dos pedidos, pagamentos, entregas e cancelamentos.

---

## 🛠️ Processo Realizado

### **1. Importação e Tratamento dos Dados (ETL)**
- Download das bases em formato CSV (pedidos, pagamentos, logística, produtos, clientes).
- Conversão de colunas de data e valores numéricos (padrão americano → brasileiro).
- Padronização da data de estimativa de entrega.
- Ordenação dos pedidos e **seleção dos 10.000 primeiros registros** para garantir boa performance no Excel.
- Integração de tabelas usando **XLOOKUP**.
- Consolidação de todas as bases em uma única planilha principal.

---

## 📈 Análises Realizadas

### 📌 **1. Cancelamentos × Entregas**
Primeiro insight importante:
- Taxa de cancelamento baixa (**0,76%**)
- Porém, o **frete dos pedidos cancelados é 74% mais caro** que o dos pedidos entregues  
➡️ Indício de **sensibilidade ao preço do frete**.

---

### 📌 **2. Valor Médio do Pedido × Status**
- Pedidos **cancelados** têm o **maior ticket médio** (R$ 259).  
- Pedidos **entregues** têm o menor (R$ 156).  
➡️ Pedidos mais caros enfrentam maior resistência na conversão.

---

### 📌 **3. Método de Pagamento × Ticket Médio**
- **Cartão de Crédito** → 75,8% das vendas | Maior ticket médio (R$ 132,06)  
- **Boleto** → 20,09% das vendas | Ticket médio intermediário (R$ 105,30)  
- **Débito e Voucher** → baixa adesão e impacto operacional reduzido

---

### 📌 **4. Tipo de Pagamento × Status do Pedido**
Transformei a tabela dinâmica em um **mapa de calor**, facilitando a leitura das relações.

**Principais descobertas:**
- **Cartão de crédito** → método mais estável (0,66% de cancelamentos | 97,82% entregues).  
- **Voucher** → maior fragilidade (5,11% de cancelamentos | 93,19% entregues).  
- **Débito** → sem cancelamentos, mas com **retenções no status “Faturado”** (0,81%).  
➡️ Indício de lentidão no processo de faturação.

---

## 📊 Produção de Gráficos e PowerPoint

Após consolidar tudo:
- Criei a aba **“Gráficos”** usando os principais resultados da aba “Resumo”.
- Montei um **PowerPoint** com:
  - Gráficos  
  - Insights  
  - Conclusões  
  - Recomendações de melhoria operacional  

📎 *O arquivo PPTX estará disponível para download no repositório.*

---

## 📝 Conclusão do Projeto

Este projeto marcou meu primeiro contato com um processo completo de análise de dados utilizando ferramentas simples, porém poderosas: **Excel e PowerPoint**.

Com ele, pude:
- Aplicar ETL com dados reais  
- Integrar diferentes bases  
- Criar indicadores e análises relevantes  
- Transformar dados em visualizações  
- Produzir uma apresentação final profissional  

Além de reforçar conceitos técnicos, esse trabalho evidenciou a importância de **traduzir números em insights acionáveis**, ajudando na tomada de decisão.  
Foi uma experiência fundamental que servirá como base sólida para desenvolver projetos mais complexos no futuro, utilizando ferramentas como SQL, Python e Power BI.

---

## 🚀 Tecnologias Utilizadas
- Microsoft Excel  
- PowerPoint  
- Funções avançadas (XLOOKUP, funções condicionais, conversões, tabelas dinâmicas)  
- Mapa de calor  
- ETL manual  

---

## ✔️ Status do Projeto
✅ Concluído  
📌 Focado no aprendizado e evolução técnica  

---
📄 **Documentação Completa do Projeto:**  
➡️ [Clique aqui para ver o Passo a Passo Completo](docs/passo-a-passo.md)
