# Varejo em Foco

**Análise exploratória do dataset Superstore**

**Autor:** Vicente Luzzi Seganfredo

**Repositório:** https://github.com/vicenteels/SuperstoreAnalysis

Este projeto apresenta uma análise exploratória do conjunto de dados `Superstore.csv`, com foco em vendas, lucro, desconto, clientes, regiões, estados e logística de entrega. O objetivo foi transformar os dados em insights práticos sobre desempenho comercial e oportunidades de melhoria.

## Aviso importante para execução

Para conseguir executar os comandos do notebook, é necessário instalar o pacote `ipykernel`. Ao rodar a primeira célula, pode aparecer o aviso:

> "Running cells with 'Python 3.12.5' requires the ipykernel package."

Nesse caso, basta clicar em **Install** ou selecionar um kernel já instalado.

## Sobre o projeto

O notebook `Analise.ipynb` foi construído para investigar o comportamento comercial dos dados e responder perguntas como:

- Como as vendas e o lucro evoluem ao longo do tempo?
- Quais categorias e subcategorias performam melhor?
- Descontos ajudam ou prejudicam o lucro?
- Quais clientes, regiões e estados mais concentram faturamento e resultado?
- O tipo de entrega impacta o tempo de logística?

## Etapas de desenvolvimento

1. Importação das bibliotecas utilizadas na análise: `pandas`, `matplotlib` e `seaborn`.
2. Leitura do arquivo `Superstore.csv`.
3. Conversão das colunas de data para o formato adequado.
4. Checagem inicial de qualidade dos dados.
5. Criação de agregações por tempo, categoria, subcategoria, cliente, região e estado.
6. Construção de gráficos para apoiar a análise exploratória.
7. Interpretação dos resultados e consolidação dos principais insights.

## Decisões de tratamento dos dados

Algumas decisões foram importantes durante a preparação da análise:

- Foram verificados valores nulos com `df.isnull().sum()` e não foi encontrado nenhum valor ausente.
- Foram verificados registros duplicados com `df.duplicated().sum()` e o retorno também foi zero.
- Como não houve nulos nem duplicados, não foi necessário aplicar imputação ou remoção de linhas por esse motivo.
- Foram identificados outliers nas variáveis `Sales` e `Profit` por meio de boxplots.
- Esses outliers foram mantidos, pois representam transações reais de alto valor e sua remoção poderia distorcer a leitura do desempenho comercial.
- A coluna de datas foi convertida para `datetime`, permitindo análises temporais e a criação da métrica de tempo de entrega.
- Foi criada a variável `Delivery Time` para comparar o desempenho logístico entre os tipos de envio.

## Principais insights da análise

### Evolução temporal

- As vendas e o lucro apresentam variações ao longo do tempo, com meses de maior concentração de receita em períodos específicos do ano.
- Os maiores picos de vendas ocorreram principalmente no fim do ano, indicando possível sazonalidade comercial.

### Categorias e subcategorias

- `Technology` foi a categoria com maior faturamento e também com maior lucro total.
- `Furniture` teve bom volume de vendas, mas desempenho de lucro bem mais tímido.
- Entre as subcategorias, `Labels`, `Paper`, `Envelopes` e `Copiers` apresentaram as melhores margens de lucro.
- `Tables`, `Bookcases` e `Supplies` apareceram com margem negativa, indicando pontos de atenção.

### Desconto x lucro

- Descontos mais agressivos se mostraram prejudiciais ao lucro médio.
- A partir de certos níveis de desconto, o resultado médio passa a ficar negativo.
- O gráfico reforça que desconto não deve ser usado de forma indiscriminada, pois pode corroer a rentabilidade.

### Clientes

- Poucos clientes concentram uma parte relevante do faturamento.
- Os 20 maiores clientes representam cerca de 11,5% do total de vendas.
- Isso mostra a importância de estratégias de fidelização e relacionamento com clientes-chave.

### Região e estados

- `West` e `East` foram as regiões com melhor desempenho em vendas e lucro.
- `Central` e `South` tiveram resultados mais modestos em faturamento.
- Entre os estados, `California`, `New York` e `Washington` lideraram o lucro.
- Já `Texas`, `Ohio` e `Pennsylvania` ficaram entre os estados com maior prejuízo acumulado.

### Logística

- `Same Day` teve o menor tempo médio de entrega.
- `Standard Class` foi o tipo de envio com maior tempo médio.
- O tempo de entrega varia de forma clara entre os modos de envio, o que ajuda a avaliar trade-offs entre custo e agilidade.

## Estrutura do projeto

- `Analise.ipynb`: notebook principal com a análise exploratória.
- `Superstore.csv`: base de dados utilizada na análise.

## Como executar o projeto

### Opção 1: Abrir no Jupyter ou VS Code

1. Abra a pasta do projeto.
2. Instale as dependências necessárias:

```bash
pip install pandas matplotlib seaborn ipykernel
```

3. Abra o arquivo `Analise.ipynb`.
4. Se solicitado, selecione ou instale um kernel Python.
5. Execute as células em ordem.

### Opção 2: Visualizar a análise

Se você não quiser executar o notebook, pode abrir o `Analise.ipynb` diretamente em um ambiente compatível com Jupyter para visualizar os gráficos e comentários.

## Dependências

- Python 3.12+
- pandas
- matplotlib
- seaborn
- ipykernel

## Observação final

A análise foi construída com foco em clareza visual e interpretação prática dos dados. O notebook serve como base para evoluções futuras, como a criação de um dashboard interativo ou novas segmentações de clientes e produtos.
