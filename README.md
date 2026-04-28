# 🤖 AI Data Cleaning

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/19wuOaTwaOXK5ynbF8BmMEdVBuirCywoc?usp=sharing)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)

> Automatiza a limpeza de datasets "sujos" usando modelos de linguagem (LLMs) para corrigir erros semânticos e inconsistências contextuais que ferramentas tradicionais como Excel ou Regex não conseguem resolver.

---

## 📌 Sobre o Projeto

Datasets do mundo real raramente chegam limpos. Erros de digitação, valores inconsistentes, campos em branco e inconsistências contextuais são comuns — e difíceis de tratar com regras fixas.

Este projeto utiliza **LLMs (Large Language Models)** para entender o contexto dos dados e fazer correções inteligentes, indo além do que expressões regulares ou heurísticas simples conseguem fazer.

### Exemplo de problema resolvido

| Antes (sujo) | Depois (limpo) |
|---|---|
| `Cofee` | `Coffee` |
| `CASH` / `cash` / `Cash` | `Cash` |
| `ERROR`, `UNKNOWN`, `` | `NaN` padronizado |
| `2023-15-03` | data inválida identificada |

---

## 🚀 Como Usar

### ▶️ Opção 1 — Google Colab (recomendado, sem instalar nada)

Clique no badge abaixo e execute direto no navegador:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/19wuOaTwaOXK5ynbF8BmMEdVBuirCywoc?usp=sharing)

> **Dica:** no Colab, vá em `Ambiente de execução → Executar tudo` para rodar o pipeline completo.

### 💻 Opção 2 — Localmente

**Pré-requisitos:** Python 3.8+

```bash
# 1. Clone o repositório
git clone https://github.com/Gu1lz/AI-Data-Cleaning.git
cd AI-Data-Cleaning

# 2. Instale as dependências
pip install -r requirements.txt

# 3. Abra o notebook
jupyter notebook Data_Cleaning.ipynb
```

---

## 📁 Estrutura do Projeto

```
AI-Data-Cleaning/
│
├── Data_Cleaning.ipynb     # Notebook principal com o pipeline de limpeza
├── dirty_cafe_sales.csv    # Dataset de exemplo (dados de vendas de cafeteria)
└── README.md               # Documentação do projeto
```

---

## 🗂️ Dataset de Exemplo

O arquivo `dirty_cafe_sales.csv` contém dados fictícios de vendas de uma cafeteria com diversos tipos de erros propositais:

- Erros de digitação nos nomes de produtos (`Cofee`, `Sandwch`)
- Valores monetários inconsistentes
- Métodos de pagamento com capitalização variada
- Campos com valores ausentes ou inválidos (`ERROR`, `UNKNOWN`)
- Datas mal formatadas

---

## ⚙️ Como Funciona

```
Dataset sujo (CSV)
        │
        ▼
┌───────────────────┐
│  Análise inicial  │  ← identifica colunas, tipos e padrões de erro
└────────┬──────────┘
         │
         ▼
┌───────────────────┐
│  Prompt ao LLM    │  ← envia amostras com contexto para o modelo
└────────┬──────────┘
         │
         ▼
┌───────────────────┐
│  Correções        │  ← o modelo retorna valores corrigidos e padronizados
└────────┬──────────┘
         │
         ▼
  Dataset limpo (CSV)
```

O LLM recebe amostras dos dados com contexto da coluna e retorna sugestões de correção que são aplicadas automaticamente ao dataset.

---

## 🛠️ Tecnologias Utilizadas

- **Python** — linguagem principal
- **Pandas** — manipulação e análise de dados
- **LLM (via API)** — núcleo da correção semântica
- **Jupyter Notebook / Google Colab** — ambiente de execução

---

## 📊 Resultados

Após rodar o pipeline no `dirty_cafe_sales.csv`:

- Valores textuais padronizados (capitalização, erros ortográficos)
- Campos inválidos (`ERROR`, `UNKNOWN`) convertidos para `NaN`
- Consistência entre colunas relacionadas verificada

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma *issue* ou enviar um *pull request*.

1. Faça um fork do projeto
2. Crie sua branch: `git checkout -b feature/minha-feature`
3. Commit suas mudanças: `git commit -m 'feat: adiciona nova feature'`
4. Push para a branch: `git push origin feature/minha-feature`
5. Abra um Pull Request

---

## 📄 Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.

---

<p align="center">Feito por <a href="https://github.com/Gu1lz">Gu1lz</a></p>
