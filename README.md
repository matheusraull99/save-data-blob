# save-data-blob

Pipeline em Python para download de dados públicos de Boston, compactação e upload para Azure Blob Storage.

## O que faz

1. **Baixa** os arquivos CSV de chamados de serviço de Boston (2015–2020) via Open Data
2. **Compacta** todos os arquivos em um `.zip`
3. **Faz upload** do arquivo compactado para um container no Azure Blob Storage

## Pré-requisitos

```bash
pip install azure-storage-blob azure-identity
```

## Como usar

1. Clone o repositório e abra o notebook `save_data_blob.ipynb`
2. Na célula de conexão, substitua `COLOCAR_SUA_CHAVE_DE_ACESSO` pela sua chave de acesso do Azure Storage
3. Execute todas as células em ordem

## Estrutura

```
save-data-blob/
├── save_data_blob.ipynb   # Notebook principal
└── data/                  # Criado em tempo de execução (CSVs baixados)
```

## Dados

- Fonte: [City of Boston Open Data](https://data.boston.gov/)
- Período: 2015 a 2020
- Formato: CSV → ZIP

## Destino no Azure

- **Storage Account:** `dadosboston`
- **Container:** `servicosbostonzip`
- **Arquivo:** `dados_boston.zip`
