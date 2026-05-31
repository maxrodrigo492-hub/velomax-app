# AutoClaw — Pacote GLM-5-Turbo + Multi-Models Setup
> Configuração completa do agente Max Representações com GLM-5-Turbo e integração de 5 modelos cloud no AutoClaw (Z.Ai).
> Gerado em 31/05/2026

---

## 📦 Pacotes Inclusos

✅ **System Prompt** — Agente virtual Max Representações (GLM-5-Turbo)  
✅ **Custom Instructions** — Diretrizes de comportamento para GLM-5-Turbo  
✅ **Claude Identity (STEP 2)** — Perfil de identidade do agente  
✅ **Knowledge Base** — Base de conhecimento completa  
✅ **Social Media Guide** — Templates para Instagram  
✅ **Multi-Models Setup** — Configuração de 5 modelos cloud no AutoClaw  

---

## 🛠️ PLANO DE INVOCAÇÃO: Modelos Cloud via Ollama

### Etapa 1️⃣: Download de Todas as Pontes (Ollama)

Abra o **PowerShell** e execute esses comandos sequencialmente:

```powershell
# Download dos 5 modelos cloud
ollama pull deepseek-v4-pro:cloud
ollama pull glm-5.1:cloud
ollama pull qwen3.5:cloud
ollama pull qwen3-coder:480b-cloud
ollama pull gemma4:31b-cloud
```

**Tempo estimado:** 10-15 minutos (depende da velocidade da internet)

---

### Etapa 2️⃣: Validação Individual (PowerShell)

Para cada modelo, execute este comando para validar se está ativo:

```powershell
# COMANDO BASE (substitua NOME_DO_MODELO_AQUI)
curl http://localhost:11434/v1/chat/completions `
  -Method POST `
  -ContentType "application/json" `
  -Body '{
    "model":"NOME_DO_MODELO_AQUI",
    "messages":[{"role":"user","content":"Olá, você está ativo?"}]
  }'
```

**Substitua `NOME_DO_MODELO_AQUI` por cada modelo:**

```powershell
# Teste 1: DeepSeek V4 Pro
curl http://localhost:11434/v1/chat/completions `
  -Method POST `
  -ContentType "application/json" `
  -Body '{
    "model":"deepseek-v4-pro:cloud",
    "messages":[{"role":"user","content":"Olá, você está ativo?"}]
  }'

# Teste 2: GLM-5.1
curl http://localhost:11434/v1/chat/completions `
  -Method POST `
  -ContentType "application/json" `
  -Body '{
    "model":"glm-5.1:cloud",
    "messages":[{"role":"user","content":"Olá, você está ativo?"}]
  }'

# Teste 3: Qwen 3.5
curl http://localhost:11434/v1/chat/completions `
  -Method POST `
  -ContentType "application/json" `
  -Body '{
    "model":"qwen3.5:cloud",
    "messages":[{"role":"user","content":"Olá, você está ativo?"}]
  }'

# Teste 4: Qwen 3 Coder 480B
curl http://localhost:11434/v1/chat/completions `
  -Method POST `
  -ContentType "application/json" `
  -Body '{
    "model":"qwen3-coder:480b-cloud",
    "messages":[{"role":"user","content":"Olá, você está ativo?"}]
  }'

# Teste 5: Gemma 4 (31B)
curl http://localhost:11434/v1/chat/completions `
  -Method POST `
  -ContentType "application/json" `
  -Body '{
    "model":"gemma4:31b-cloud",
    "messages":[{"role":"user","content":"Olá, você está ativo?"}]
  }'
```

✅ **Se todos retornarem `StatusCode: 200`, prossiga para a próxima etapa.**

---

### Etapa 3️⃣: Invocação no AutoClaw (Configuração Final)

Abra o **AutoClaw** → **Add Model** e preencha as 5 fichas conforme abaixo.

**⚠️ IMPORTANTE:** Em TODAS as fichas:
- `Base URL`: `http://localhost:11434/v1`
- `API Protocol`: `OpenAI`

---

## 📋 FICHAS DE CONFIGURAÇÃO DOS MODELOS

### 1️⃣ DeepSeek V4 Pro (Máxima Inteligência)

| Campo | Valor |
|-------|-------|
| **Model ID** | `deepseek-v4-pro:cloud` |
| **Display Name** | `DeepSeek V4 Pro (Max)` |
| **Base URL** | `http://localhost:11434/v1` |
| **API Protocol** | `OpenAI` |
| **Z.ai API Key** | `ollama` |
| **Context Window** | `100000` |
| **Max Output Tokens** | `8192` |
| **Temperatura** | `0.7` |
| **Top P** | `0.9` |

**Usar para:** Análises profundas, pesquisas de mercado, estratégia comercial

---

### 2️⃣ GLM-5.1 (Agent Expert - Principal para Max)

| Campo | Valor |
|-------|-------|
| **Model ID** | `glm-5.1:cloud` |
| **Display Name** | `GLM 5.1 (Agent Expert)` |
| **Base URL** | `http://localhost:11434/v1` |
| **API Protocol** | `OpenAI` |
| **Z.ai API Key** | `ollama` |
| **Context Window** | `32000` |
| **Max Output Tokens** | `4096` |
| **Temperatura** | `0.7` |
| **Top P** | `0.9` |

**Usar para:** ⭐ **Agente padrão da Max Representações** — Vendas, orçamentos, atendimento técnico

---

### 3️⃣ Qwen 3.5 (Estável & Rápido)

| Campo | Valor |
|-------|-------|
| **Model ID** | `qwen3.5:cloud` |
| **Display Name** | `Qwen 3.5 (Stable)` |
| **Base URL** | `http://localhost:11434/v1` |
| **API Protocol** | `OpenAI` |
| **Z.ai API Key** | `ollama` |
| **Context Window** | `32000` |
| **Max Output Tokens** | `4096` |
| **Temperatura** | `0.7` |
| **Top P** | `0.9` |

**Usar para:** Conteúdo de marketing, redes sociais, respostas rápidas

---

### 4️⃣ Qwen 3 Coder 480B (Programação & Análise Técnica)

| Campo | Valor |
|-------|-------|
| **Model ID** | `qwen3-coder:480b-cloud` |
| **Display Name** | `Qwen 3 Coder (480B)` |
| **Base URL** | `http://localhost:11434/v1` |
| **API Protocol** | `OpenAI` |
| **Z.ai API Key** | `ollama` |
| **Context Window** | `128000` |
| **Max Output Tokens** | `8192` |
| **Temperatura** | `0.3` |
| **Top P** | `0.95` |

**Usar para:** Código, análise técnica profunda, documentação de produtos

---

### 5️⃣ Gemma 4 (31B - Balanced)

| Campo | Valor |
|-------|-------|
| **Model ID** | `gemma4:31b-cloud` |
| **Display Name** | `Gemma 4 (31B Cloud)` |
| **Base URL** | `http://localhost:11434/v1` |
| **API Protocol** | `OpenAI` |
| **Z.ai API Key** | `ollama` |
| **Context Window** | `64000` |
| **Max Output Tokens** | `4096` |
| **Temperatura** | `0.7` |
| **Top P** | `0.9` |

**Usar para:** Suporte técnico, descrições de produtos, consultorias gerais

---

## ✅ CHECKLIST DE VERIFICAÇÃO FINAL

- [ ] **Ollama Server** rodando na porta `11434`
- [ ] **OpenClaw Gateway** rodando na porta `18789`
- [ ] **5 modelos** baixados com sucesso via `ollama pull`
- [ ] **5 testes de validação** retornando `StatusCode 200`
- [ ] **5 modelos** configurados no AutoClaw com Display Names corretos
- [ ] **GLM-5.1** selecionado como modelo padrão para agente Max
- [ ] **Knowledge Base** (`04-knowledge-base.md`) carregada no workspace
- [ ] **System Prompt** configurado no AutoClaw
- [ ] **Custom Instructions** ativas
- [ ] **Agent Identity** preenchida com dados de Rodrigo

---

## 🎯 RECOMENDAÇÕES DE USO

| Situação | Modelo Recomendado |
|----------|-------------------|
| Vendas e atendimento ao cliente | **GLM-5.1** ⭐ |
| Análise de mercado e estratégia | **DeepSeek V4 Pro** 🔝 |
| Conteúdo para redes sociais | **Qwen 3.5** 📱 |
| Desenvolvimento técnico | **Qwen 3 Coder 480B** 💻 |
| Suporte geral e consultorias | **Gemma 4** 🤝 |

---

## 📞 CONTATOS - Max Representações

| Canal | Contato |
|-------|---------|
| **WhatsApp 1** | (43) 99916-5693 |
| **WhatsApp 2** | (43) 98492-9956 |
| **E-mail** | maxrepresentacoesofc@gmail.com |
| **Instagram** | @maxrepresentacoesofc |
| **Site** | https://maxrepresentacoes.base44.app/ |
| **Horário** | Ter-Sab: 08h-18h \| Dom: 08h-12h |

---

## 🚀 PRÓXIMOS PASSOS

1. Execute os comandos `ollama pull` no PowerShell
2. Valide cada modelo com os testes de curl
3. Configure os 5 modelos no AutoClaw conforme as fichas acima
4. Selecione **GLM-5.1** como modelo padrão
5. Carregue a Knowledge Base
6. Teste com uma pergunta simples sobre produtos Max
7. Pronto! Seu agente virtual estará 100% operacional ✅

---

**Status:** ✅ Pronto para Deploy  
**Atualizado:** 31/05/2026  
**Versão:** AutoClaw GLM-5-Turbo v1.0
