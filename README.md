# 🚀 Case de Retenção Claro: AI & Predictive Analytics

![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-1.7-F37626?style=for-the-badge&logo=xgboost&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

## 📌 Visão Geral
Este projeto foi desenvolvido como case técnico para estruturar um modelo preditivo de retenção de clientes. O objetivo principal é identificar de forma assertiva o perfil dos clientes da base (jun/2025 - dez/2025) que aceitam ofertas e realizam movimentações de produtos durante o funil de retenção.

O pipeline contempla desde a engenharia de features e tratamento de nulos lógicos, até o treinamento de um modelo **XGBoost Classifier** otimizado para lidar com classes desbalanceadas. O projeto culmina na extração de explicabilidade com **SHAP Values** para suporte à decisão de negócios.

## 🏗️ Arquitetura do Projeto
Para garantir total reprodutibilidade, o ambiente foi conteinerizado em uma arquitetura multi-serviços usando Docker Compose:
* **Jupyter Lab Service (Porta 8888):** Ambiente de desenvolvimento e execução do notebook analítico.
* **Dashboard Service (Porta 8000):** Servidor HTTP leve exibindo um painel executivo interativo HTML/JS com os resultados consolidados (alimentado via JSON).

## 📊 Principais Métricas em Validação (K-Fold CV)
* **AUC-ROC:** ~0.68 (Comprovada estabilidade via K-Fold)
* **KS (Kolmogorov-Smirnov):** > 26.0% (Modelo maduro para esteiras de CRM)
* **Conclusão Estratégica:** A ferramenta "Solar" (29.8% de conversão) supera a recomendação via catálogo "Legado" (24.0%). O perfil de aceitação é fortemente ditado pelo ticket atual de TV e Banda Larga.

## ⚙️ Como Executar (Instruções de Build)

**Pré-requisitos:** Ter o [Docker](https://www.docker.com/) e o `docker-compose` instalados na máquina.

1. Clone ou extraia este repositório.
2. Abra o terminal na raiz do projeto e execute o comando:
   ```bash
   docker-compose up --build -d
   ```

3. Aguarde o download e a construção das imagens.

4. Acesse as Interfaces:

📓 Notebook (Jupyter Lab): http://localhost:8888

📈 Dashboard Executivo: http://localhost:8000

(Nota: O Jupyter Lab está configurado para acessar sem necessidade de token para facilitar a avaliação técnica).

## 📁 Estrutura de Diretórios:
    ```yaml
    /
    ├── data/                  # Arquivos de dados originais (.xlsx, .parquet)
    ├── dashboard/             # Assets do painel web (index.html, .json, .png)
    ├── notebooks/             # Código fonte principal (.ipynb)
    ├── docker-compose.yml     # Orquestração dos microserviços
    ├── Dockerfile             # Imagem do Jupyter com dependências Python
    └── requirements.txt       # Mapeamento de bibliotecas
    ```
