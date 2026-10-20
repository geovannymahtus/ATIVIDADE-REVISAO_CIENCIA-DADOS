# Revisão — Limpeza e Preparação de Dados

Ciência de Dados · Etapa CRISP-DM: Preparação dos Dados

Cinco notebooks, um por exercício da lista. Todos já estão **executados**: dá para abrir e ver as tabelas, os gráficos e as respostas sem rodar nada.

## Estrutura

| Pasta | Tema | Dataset | Destaques |
|---|---|---|---|
| `ex1/` | Valores ausentes | Melbourne Housing (`melb_data.csv`) | imputação pela mediana **do grupo** (tipo de imóvel, quartos, bairro); `CouncilArea` deixa de ser registrada a partir de ago/2017; KNN validado contra a mediana |
| `ex2/` | Duplicatas | KPMG (`KPMG_VI_New_raw_data_update_final.xlsx`) | leitura que encontra o cabeçalho sozinha; "escada" de critérios de duplicata; cliente órfão 5034; simulação de carga dobrada com consolidação |
| `ex3/` | Padronização e escalonamento | Adult Census (`adult.data` + `adult.test`) | `>50K.` com ponto no arquivo de teste; escalonador ajustado só no treino; fórmulas conferidas na mão |
| `ex4/` | Outliers | Diamonds (`sns.load_dataset`) | critério de erro pela **densidade** (peso compatível com o tamanho); remoção por Z-score, capping p1–p99, log10 |
| `ex5/` | Pipeline integrado | SHEIN: calçados + esportes (21 CSVs) | pergunta "mais cores = mais ranking?"; consolidação de duplicatas; z-score robusto (MAD); pipeline aplicado nos 21 arquivos |

## Como rodar de novo

```bash
pip install -r requirements.txt
cd ex1
jupyter notebook exercicio_1.ipynb
```

Ou, para reexecutar tudo de uma vez dentro da pasta de cada exercício:

```bash
python -m jupyter nbconvert --to notebook --execute --inplace exercicio_N.ipynb
```

Os dados já estão dentro de cada pasta. O do exercício 4 vem do seaborn (precisa de internet na primeira execução).

## Fontes dos dados

- Melbourne Housing Snapshot — https://www.kaggle.com/datasets/dansbecker/melbourne-housing-snapshot
- KPMG Customer Transactions — https://www.kaggle.com/datasets/archit9406/customer-transaction-dataset
- Adult Census Income — https://archive.ics.uci.edu/dataset/2/adult
- Diamonds — repositório de datasets do seaborn
- Dirty E-Commerce Data (SHEIN) — https://www.kaggle.com/datasets/oleksiimartusiuk/e-commerce-data-shein
