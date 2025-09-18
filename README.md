# Desafio Auditor Sr. Analytics — Datasets e Instruções Base
Repositório com os **arquivos de dados** e **instruções-base** para o desafio técnico da vaga de Auditor Sr. Analytics na área de Auditoria Contínua, Metodologia e IA.

> Estes dados são fictícios e destinados exclusivamente ao processo seletivo.

---

## 1. Conteúdo deste repositório

- `data/transacoes.csv`  
  Transações financeiras simuladas, com outliers, possíveis violações de controle (aprovação por IA sem dupla aprovação manual) e padrões de fracionamento (smurfing).

- `data/logs_ia.csv`  
  Logs de interações com um assistente de IA generativa, incluindo tentativas de **prompt injection** e uma tendência simulada de aumento de **FALHA** nos últimos 30 dias (possível *drift*).

- `DATA_DICTIONARY.md`  
  Dicionário de dados descrevendo colunas, tipos e notas de uso.

---

## 2. Objetivo do desafio (síntese)

O candidato deverá:
1. Ingerir e explorar os dados com **PySpark** (Spark local ou HDFS).
2. Construir indicadores de risco e avaliar a **aderência a controles** (por exemplo, transações acima de um limiar que exigem aprovação manual).
3. Detectar **anomalias** (outliers, smurfing, horários incomuns).
4. Produzir **visualizações** que sustentem os achados.
5. Integrar uma **API de LLM** (Google Gemini) para analisar trechos de `logs_ia.csv` e/ou gerar hipóteses, com **validação crítica** do resultado.
6. Auditar riscos de IA: identificar tentativas de **prompt injection** e discutir sinais/monitoramento de **drift**.
7. Documentar a solução em **README** próprio, com decisões, suposições e recomendações.
8. Publicar a solução em repositório GitHub próprio e conceder acesso ao usuário **`BrunoAraujo84`**.

---

## 3. Como obter os dados

### Opção A — Git
```bash
git clone https://github.com/<seu-usuario>/Vaga_Sr_Auditoria_Continua_Metodologia_e_IA.git
cd Vaga_Sr_Auditoria_Continua_Metodologia_e_IA
```

### Opção B — Download direto
Baixe os arquivos `transacoes.csv` e `logs_ia.csv` da pasta `data/` deste repositório e o `DATA_DICTIONARY.md`.

---

## 4. Requisitos mínimos esperados na solução do candidato

- **Python + PySpark** para ingestão e análise.
- **SQL/Spark SQL** nas consultas e indicadores.
- **LLM (Google Gemini)** via API, com chave gerenciada via `.env` (não versionar a chave).
- **Visualizações** com leitura clara dos resultados.
- **README (relatório)** explicando decisões, suposições (por exemplo, limiar para dupla aprovação), KPIs, gráficos e recomendações.
- **Boas práticas** de organização do repositório.

---

## 5. Estrutura sugerida para o repositório do candidato

```
.
├─ README.md                 # Relatório principal
├─ requirements.txt          # ou pyproject.toml/poetry.lock
├─ .env.example              # placeholders de variáveis (não subir .env real)
├─ data/
│  ├─ transacoes.csv
│  └─ logs_ia.csv
├─ notebooks/
│  ├─ 01_eda.ipynb
│  ├─ 02_indicadores.ipynb
│  └─ 03_llm_logs.ipynb
├─ src/
│  ├─ ingestao_spark.py
│  ├─ indicadores.py
│  ├─ anomalias.py
│  ├─ llm_auditoria.py
│  └─ utils/
└─ dashboards/
   └─ figuras/
```

---

## 6. Publicação e compartilhamento para avaliação

1. Criar um repositório próprio (público ou privado) para a solução.
2. Subir o código e a documentação.
3. Adicionar o usuário **`BrunoAraujo84`** como colaborador (Settings → Collaborators → Add people).
4. Enviar o link do repositório dentro do prazo definido.
5. (Opcional) Criar uma tag (por exemplo, `v1.0-entrega`) e uma release com breve descrição.

---

## 7. Licença e uso

Dados e materiais disponibilizados exclusivamente para uso no processo seletivo. Reprodução, redistribuição ou uso fora deste contexto não é permitido.
