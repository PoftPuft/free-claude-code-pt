<div align="center">

<h1>
  <picture>
    <source media="(prefers-color-scheme: light)" srcset="assets/free-claude-code-wordmark-light.svg">
    <img src="assets/free-claude-code-wordmark-dark.svg" alt="Free Claude Code" width="610">
  </picture>
</h1>

[![Licença: AGPL v3](https://img.shields.io/badge/Licença-AGPL_v3-2e7d32.svg?style=for-the-badge)](https://github.com/PoftPuft/free-claude-code-pt/blob/main/LICENSE)
[![Python 3.14](https://img.shields.io/badge/python-3.14-3776ab.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![Gerenciador de Pacotes: uv](assets/package-manager-uv.svg)](https://github.com/astral-sh/uv)
[![Testes: Pytest](https://img.shields.io/badge/Testes-Pytest-ad1457.svg?style=for-the-badge)](https://github.com/pytest-dev/pytest)
[![Verificador de Tipos: Pyrefly](https://img.shields.io/badge/Verificador%20de%20Tipos-pyrefly-fdd835.svg?style=for-the-badge)](https://github.com/pyrefly-org/pyrefly)
[![Formatador: Ruff](https://img.shields.io/badge/Formatador-ruff-bf4b00.svg?style=for-the-badge)](https://github.com/astral-sh/ruff)
[![Logging: Loguru](https://img.shields.io/badge/logging-loguru-00695c.svg?style=for-the-badge)](https://github.com/Delgan/loguru)

[Início Rápido](#início-rápido) · [Provedores](#escolha-um-provedor) · [Integrações](#integrações) · [API](#use-a-api-diretamente) · [Celular](#use-do-seu-celular) · [Gerenciar](#gerencie-sua-instalação)

</div>

<p align="center">
  <em>Projeto open-source independente. Não afiliado ou endossado pela Anthropic. Claude e Claude Code são marcas registradas da Anthropic.</em>
</p>

---

## 📋 Índice

1. [Visão Geral](#visão-geral)
2. [Recursos](#recursos)
3. [Início Rápido](#início-rápido)
   - [Passo 1: Instalação](#passo-1-instalação)
   - [Passo 2: Iniciar FCC](#passo-2-iniciar-fcc)
   - [Passo 3: Configurar NVIDIA NIM](#passo-3-configurar-nvidia-nim)
   - [Passo 4: Executar seu Agente de Codificação](#passo-4-executar-seu-agente-de-codificação)
4. [Escolha um Provedor](#escolha-um-provedor)
5. [Integrações](#integrações)
6. [Use a API Diretamente](#use-a-api-diretamente)
7. [Use do seu Celular](#use-do-seu-celular)
8. [Gerencie sua Instalação](#gerencie-sua-instalação)
9. [Links do Projeto](#links-do-projeto)
10. [Licença](#licença)

---

## Visão Geral

O **Free Claude Code (FCC)** é um proxy local que permite usar qualquer modelo de IA (gratuito ou pago) com seus agentes de codificação favoritos como Claude Code, Codex, Pi, OpenCode, Cline, Hermes, DeepSeek Harness, Grok Build, Muse Code, Aider, Antigravity CLI e VS Code Chat.

### Por que usar o FCC?

- 🆓 **Acesso gratuito** a modelos premium através de 60+ provedores
- 🔄 **Roteamento inteligente** com fallback automático entre modelos/provedores
- 📱 **Use no celular** via Discord ou Telegram com suporte a notas de voz
- 🖥️ **Integração nativa** com VS Code, JetBrains, apps desktop
- ⚡ **Otimização de tokens** até 90% menos uso com RTK + Headroom
- 🛡️ **Confiabilidade** com retentativas automáticas, rate limiting, controle de concorrência

---

## Recursos

### Agentes de Codificação Suportados (12)
| Agente | Comando | Descrição |
|--------|---------|-----------|
| Claude Code | `fcc-claude` | Agente oficial da Anthropic |
| Codex | `fcc-codex` | Agente da OpenAI |
| Pi | `fcc-pi` | Agente da Earendil Works |
| OpenCode 2 | `fcc-opencode` | Agente da Anomaly |
| Cline | `fcc-cline` | Extensão VS Code popular |
| Hermes | `fcc-hermes` | Agente da Nous Research |
| DeepSeek Harness | `fcc-dsh` | Agente da DeepSeek |
| Grok Build | `fcc-grok` | Agente da xAI |
| Muse Code | `fcc-muse` | Agente da Meta |
| Aider | `fcc-aider` | Pair programming no terminal |
| Antigravity CLI | `fcc-agy` | CLI do Google |
| VS Code Chat | Nativo | Chat integrado no VS Code |

### 4 APIs Suportadas
- **Anthropic Messages** (`/v1/messages`)
- **OpenAI Chat Completions** (`/v1/chat/completions`)
- **OpenAI Responses** (`/v1/responses`)
- **Gemini** (`generateContent`)

### 61+ Provedores
Incluindo: NVIDIA NIM, OpenRouter, Groq, OpenAI/ChatGPT, GitHub Copilot, xAI (Grok), Alibaba Cloud, QwenCloud, Together AI, DeepInfra, SiliconFlow, Nebius, Chutes, Featherless AI, Agnes AI, ZenMux, W&B Inference, Anthropic, Azure OpenAI, Google AI Studio, Google Vertex AI, DeepSeek, Mistral, Amazon Bedrock, Hugging Face, Cohere, Wafer, Kimi, MiniMax, Cerebras, SambaNova, Fireworks AI, Novita AI, Cloudflare, Z.ai, TokenRouter, NaraRoute, Poolside AI, e muitos mais.

> **Total estimado: 1.3B+ tokens gratuitos por mês** entre todos os provedores.

---

## Início Rápido

### Passo 1: Instalação

#### Windows PowerShell (Recomendado)

```powershell
# Instalação básica
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.ps1")))

# Com suporte a voz local (Whisper)
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.ps1"))) -VoiceLocal

# Com suporte a voz local + CUDA 13.0
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.ps1"))) -VoiceLocal -TorchBackend cu130

# Com otimização de tokens RTK + Headroom
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.ps1"))) -RtkHeadroom

# Apenas atualização (pula se já estiver na versão mais recente)
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.ps1"))) -Update
```

#### macOS / Linux

```bash
# Instalação básica
curl -fsSL "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.sh" | sh

# Com suporte a voz local (Whisper)
curl -fsSL "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.sh" | sh -s -- --voice-local

# Com suporte a voz local + CUDA 13.0
curl -fsSL "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.sh" | sh -s -- --voice-local --torch-backend cu130

# Com otimização de tokens RTK + Headroom
curl -fsSL "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.sh" | sh -s -- --rtk-headroom

# Apenas atualização
curl -fsSL "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.sh" | sh -s -- --update
```

#### O que acontece durante a instalação?

1. **Verifica pré-requisitos**: curl, bash/sh, mktemp, tar (para RTK)
2. **Instala/atualiza uv** (gerenciador de pacotes Python rápido)
3. **Pergunta quais agentes instalar** (modo interativo):
   - ✅ Claude Code
   - ✅ Codex
   - ✅ Pi
   - ✅ OpenCode
   - ⬜ Cline
   - ✅ Hermes
   - ✅ DeepSeek Harness
   - ✅ Grok Build
   - ✅ Muse Code
   - ✅ Aider
   - ✅ Antigravity CLI
4. **Pergunta sobre RTK + Headroom** (otimização de tokens até 90%)
5. **Instala agentes selecionados** automaticamente
6. **Instala FCC** via `uv tool install`
7. **Configura PATH** e verifica instalação
8. **Instala app desktop** (macOS) / atalho (Windows)

> **Dica**: Selecione pelo menos um agente. Recomendamos manter Claude Code, Codex e OpenCode ativados.

---

### Passo 2: Iniciar FCC

#### Windows
- Abra **Free Claude Code** no Menu Iniciar ou na Área de Trabalho
- Ou execute no terminal: `fcc-server`
- Mantenha o terminal aberto enquanto usa

#### macOS
- Abra **Free Claude Code** no Launchpad ou pasta Aplicativos
- Ou execute no terminal: `fcc-server`
- Use o ícone na barra de menu para abrir Admin, reiniciar ou sair

#### Linux
```bash
fcc-server
```
- Mantenha o terminal aberto
- A URL do Admin UI aparecerá nos logs

#### Verificar se está rodando
```bash
fcc-server --version
# Deve mostrar a versão instalada
```

---

### Passo 3: Configurar NVIDIA NIM (Provedor Recomendado Gratuito)

O **NVIDIA NIM** oferece modelos gratuitos generosos e é o provedor padrão recomendado.

#### 1. Obter API Key
1. Acesse: https://build.nvidia.com/settings/api-keys
2. Faça login com conta NVIDIA (gratuita)
3. Clique em **"Generate API Key"**
4. Copie a chave (começa com `nvapi-`)

#### 2. Abrir Admin UI
- No terminal do `fcc-server`, procure por:
  ```
  Admin UI: http://127.0.0.1:8082/admin
  ```
- Abra essa URL no navegador

#### 3. Configurar Provedor
1. No menu lateral, clique em **Providers** (Provedores)
2. Encontre **NVIDIA NIM** na seção "Cloud providers"
3. Clique em **Configure** → **Add key**
4. Cole sua API key e clique **Save**
5. O modelo padrão `nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b` já está selecionado
6. Clique **Apply** no topo da página

#### 4. (Opcional) Proteger com Token
- Em **Admin UI → Settings → Proxy Authentication**: ative
- Gere um token e use como API key nos clientes

---

### Passo 4: Executar seu Agente de Codificação

Agora que o FCC está rodando e configurado, inicie seu agente preferido:

```bash
# Claude Code (recomendado)
fcc-claude

# Codex (OpenAI)
fcc-codex

# Pi
fcc-pi

# OpenCode 2
fcc-opencode

# Cline
fcc-cline

# Hermes
fcc-hermes

# DeepSeek Harness
fcc-dsh

# Grok Build
fcc-grok

# Muse Code
fcc-muse

# Aider
fcc-aider

# Antigravity CLI
fcc-agy
```

#### No Claude Code: Selecionar Modelo
1. Digite `/model` no Claude Code
2. Escolha um modelo FCC (ex: `nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b`)
3. Comece a codificar!

---

## Escolha um Provedor

### Guia Rápido de Configuração

| Provedor | Link da API Key | Configuração no Admin UI | Modelo Exemplo |
|----------|-----------------|--------------------------|----------------|
| **NVIDIA NIM** ⭐ | [build.nvidia.com](https://build.nvidia.com/settings/api-keys) | `NVIDIA_NIM_API_KEY` | `nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b` |
| **OpenRouter** | [openrouter.ai/keys](https://openrouter.ai/keys) | `OPENROUTER_API_KEY` | `open_router/openrouter/free` |
| **Groq** | [console.groq.com/keys](https://console.groq.com/keys) | `GROQ_API_KEY` | `groq/llama-3.3-70b-versatile` |
| **OpenAI/ChatGPT** | [Conectar via OAuth](https://learn.chatgpt.com/docs/auth) | Providers → OAuth → OpenAI | `openai/gpt-5.6-sol` |
| **GitHub Copilot** | [Conectar via OAuth](https://docs.github.com/en/copilot/how-tos/copilot-sdk/auth/authenticate) | Providers → OAuth → GitHub Copilot | `github_copilot/gpt-4o` |
| **xAI (Grok)** | [console.x.ai](https://console.x.ai/team/default/api-keys) | `XAI_API_KEY` | `xai/grok-4.5` |
| **Google AI Studio** | [aistudio.google.com/apikey](https://aistudio.google.com/apikey) | `GEMINI_API_KEY` | `gemini/models/gemini-3.1-flash-lite` |
| **DeepSeek** | [platform.deepseek.com](https://platform.deepseek.com/api_keys) | `DEEPSEEK_API_KEY` | `deepseek/deepseek-chat` |
| **Mistral** | [console.mistral.ai](https://console.mistral.ai/) | `MISTRAL_API_KEY` | `mistral/devstral-small-latest` |
| **Together AI** | [api.together.ai](https://api.together.ai/settings/api-keys) | `TOGETHER_API_KEY` | `together/zai-org/GLM-5.2` |

### Configuração Detalhada por Provedor

#### OpenAI / ChatGPT (Assinatura)
1. Admin UI → **Providers → OAuth providers**
2. Clique **Connect** em "OpenAI / ChatGPT"
3. Complete login no navegador
4. Reinicie o agente já rodando

#### Anthropic (API Key Separada)
1. Admin UI → **Providers → Cloud providers → Anthropic → Configure**
2. Adicione `ANTHROPIC_API_KEY`
3. Para multi-workspace: adicione `ANTHROPIC_WORKSPACE_ID`

#### GitHub Copilot
1. Instale [Copilot CLI 1.0.83+](https://github.com/github/copilot-cli/releases/tag/v1.0.83) no PATH
2. Admin UI → **Providers → OAuth providers → GitHub Copilot → Connect**
3. Complete login, reinicie o agente

#### Azure OpenAI
1. Defina `AZURE_OPENAI_BASE_URL` (ex: `https://SEU-RECURSO.openai.azure.com/openai/v1/`)
2. Defina `AZURE_OPENAI_API_KEY`
3. Selecione deployment que suporte Chat Completions

#### Modelos Locais (Ollama, LM Studio, llama.cpp)

**Ollama:**
```bash
ollama pull llama3.1
ollama serve
```
Use prefixo `ollama/` + tag do `ollama list`

**LM Studio:**
1. Inicie servidor local no LM Studio
2. Carregue modelo com suporte a tools
3. Use `lmstudio/` + identificador do modelo

**llama.cpp:**
```bash
llama-server -m modelo.gguf --ctx-size 32768
```
Use `llamacpp/` + ID do modelo local

---

### Roteamento por Tier de Modelo (Opcional)

No **Admin UI → Model Config**, você pode definir modelos específicos para cada tier do Claude Code:

| Configuração | Descrição |
|-------------|-----------|
| `MODEL` | Fallback para todas as requisições |
| `MODEL_FABLE` | Override para tier Fable |
| `MODEL_OPUS` | Override para tier Opus |
| `MODEL_SONNET` | Override para tier Sonnet |
| `MODEL_HAIKU` | Override para tier Haiku |

**Fallback Models**: Lista ordenada de modelos para tentar se o principal falhar. Cada fallback tem seu próprio nível de reasoning.

---

### Controle de Reasoning

**Admin UI → Model Config → Model Routing**

| Seleção | Comportamento |
|---------|---------------|
| **From client** | Usa effort enviado pelo agente (padrão) |
| **Off** | Desabilita reasoning |
| **Low/Medium/High/X-High/Max** | Força nível específico |
| **Inherit** | Tier usa Default Effort; fallbacks mantêm effort original |

---

## Integrações

Os launchers do FCC iniciam o servidor automaticamente.

### Editores e Apps

1. Instale o cliente
2. Inicie o FCC (`fcc-server` ou app desktop)
3. Abra **Admin UI → Integrations**
4. Clique **Connect** no card do cliente

| Cliente | Instruções |
|---------|------------|
| **Claude Code no VS Code** | Instale [extensão Claude Code](https://marketplace.visualstudio.com/items?itemName=anthropic.claude-code) |
| **VS Code Chat** | Instale VS Code mais recente, conecte, selecione modelo FCC no picker nativo |
| **Claude Desktop** | Instale [Claude Desktop](https://claude.ai/download), **feche completamente** antes de conectar/desconectar |
| **Codex no VS Code/App** | Instale [extensão Codex](https://marketplace.visualstudio.com/items?itemName=openai.chatgpt) ou Codex App |
| **DeepSeek Harness Desktop** | Instale e abra uma vez antes de conectar. Nova sessão para usar modelos FCC |
| **Claude Code no JetBrains** | Instale Claude Agent no JetBrains AI Assistant, inicie uma vez, clique Connect no FCC. Reabra IDE, selecione "Claude Code (FCC)" |

> **Importante**: Recarregue VS Code ou reinicie o app/IDE após conectar. Em Codex e Claude Desktop, selecione modelo FCC no picker.

---

## Use a API Diretamente

Qualquer cliente/SDK compatível pode chamar o FCC diretamente.

### URLs Base
- **OpenAI clients**: `http://127.0.0.1:8082/v1`
- **Anthropic/Gemini clients**: `http://127.0.0.1:8082`

### Autenticação (se Proxy Authentication ativado)
```bash
# Como API key
-H "Authorization: Bearer SEU_TOKEN"

# Ou defina como API key no cliente
```

### Listar Modelos Disponíveis
```bash
curl "http://127.0.0.1:8082/v1/models?view=messages"
```

### Exemplos de Requisição

#### Anthropic Messages API
```bash
curl http://127.0.0.1:8082/v1/messages \
  -H "Content-Type: application/json" \
  -d '{
    "model": "nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b",
    "max_tokens": 1024,
    "messages": [{"role": "user", "content": "Olá!"}]
  }'
```

#### OpenAI Chat Completions
```bash
curl http://127.0.0.1:8082/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b",
    "messages": [{"role": "user", "content": "Olá!"}]
  }'
```

#### OpenAI Responses API
```bash
curl http://127.0.0.1:8082/v1/responses \
  -H "Content-Type: application/json" \
  -d '{
    "model": "nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b",
    "input": "Olá!"
  }'
```

#### Gemini API
```bash
curl http://127.0.0.1:8082/v1/models/nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b:generateContent \
  -H "Content-Type: application/json" \
  -d '{"contents": [{"role": "user", "parts": [{"text": "Olá!"}]}]}'
```

### Streaming
- **Responses**: Sempre faz streaming
- **Messages/Chat Completions**: Adicione `"stream": true`
- **Gemini**: Use `:streamGenerateContent?alt=sse` em vez de `:generateContent`

---

## Use do seu Celular

Execute tarefas de codificação via Discord ou Telegram, com suporte a notas de voz.

### Bot do Discord

1. Crie bot no [Discord Developer Portal](https://discord.com/developers/applications)
2. Ative **Message Content Intent**
3. Convide com permissões: read, send, message-history, **Manage Messages** (para `/clear`)
4. Admin UI → **Messaging** → **Messaging Platform**: `discord`
5. Preencha:
   - **Discord Bot Token**
   - **Allowed Discord Channels** (IDs dos canais)
   - **Allowed Directory** (caminho absoluto do projeto)
6. **Apply** e reinicie se solicitado

### Bot do Telegram

1. Crie bot com [@BotFather](https://t.me/BotFather)
2. Obtenha seu User ID numérico em [@userinfobot](https://t.me/userinfobot)
3. Em grupos: dê permissão ao bot para deletar mensagens
4. Admin UI → **Messaging** → **Messaging Platform**: `telegram`
5. Preencha:
   - **Telegram Bot Token**
   - **Allowed Telegram User ID**
   - **Allowed Directory** (caminho absoluto)
6. **Apply** e reinicie se solicitado

### Comandos de Mensagem

| Comando | Comportamento |
|---------|---------------|
| `/stats` | Mostra estado da sessão |
| `/stop` (sozinho) | Cancela todo trabalho |
| Reply com `/stop` | Cancela apenas a requisição selecionada |
| `/clear` (sozinho) | Limpa todas conversas FCC neste chat |
| Reply com `/clear` | Deleta mensagem selecionada e cadeia de respostas |

### Notas de Voz

**NVIDIA NIM** (incluso em toda instalação):
1. Admin UI → **Messaging → Voice**
2. Ative voice notes, selecione `nvidia_nim`, escolha modelo
3. Configure **NVIDIA NIM API key** na página Providers

**Whisper Local (CPU/CUDA)** - Reinstale com opção:
```bash
# macOS/Linux
curl -fsSL "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.sh" | sh -s -- --voice-local

# Com CUDA 13.0
curl -fsSL "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.sh" | sh -s -- --voice-local --torch-backend cu130

# Windows PowerShell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.ps1"))) -VoiceLocal

# Com CUDA 13.0
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.ps1"))) -VoiceLocal -TorchBackend cu130
```

Após instalar, reinicie `fcc-server`. Em **Admin UI → Messaging → Voice**, ative, selecione `cpu` ou `cuda`, escolha modelo Whisper. Modelos gateados precisam de `HUGGINGFACE_API_KEY`.

---

## Gerencie sua Instalação

### Verificar Versão
```bash
fcc-server --version
```

### Atualizar
```bash
# Pare todos comandos FCC rodando, então:
fcc-update
```

`fcc-update` instala a versão mais recente a menos que você já a tenha.

Se falhar, execute o [comando de instalação](#passo-1-instalação) novamente.

Para reinstalar ou mudar componentes opcionais:
```bash
# Com voz local
curl -fsSL "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.sh" | sh -s -- --voice-local --torch-backend cu130

# Windows
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install.ps1"))) -VoiceLocal -TorchBackend cu130
```

### Muse Code no Windows Nativo
```powershell
# Instalar/atualizar apenas Muse Code
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/install-muse.ps1")))

# Remover cópia do Muse Code instalada pelo FCC (mantém dados)
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/uninstall-muse.ps1")))
```

Desinstalar FCC deixa Muse Code instalado.

### Desinstalar

**Pare todos comandos FCC e feche apps conectados antes.**

#### Remove
- Free Claude Code (launcher desktop, comandos)
- `~/.fcc/`

#### Mantém
- uv e Python
- Seus agentes de codificação, RTK, Headroom

#### macOS/Linux
```bash
curl -fsSL "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/uninstall.sh" | sh
```

#### Windows PowerShell
```powershell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/PoftPuft/free-claude-code-pt/main/scripts/uninstall.ps1")))
```

---

## Links do Projeto

Para problemas após instalação, execute e envie a saída no relatório:

```bash
fcc-doctor
```

- [Reportar bugs ou solicitar funcionalidades](https://github.com/PoftPuft/free-claude-code-pt/issues)
- [Guia de contribuição](CONTRIBUTING.md)

---

## Licença

GNU Affero General Public License versão 3 apenas (`AGPL-3.0-only`). Veja [LICENSE](LICENSE) para detalhes.

---

## 📝 Créditos

**Tradução e adaptação para português**: [PoftPuft](https://github.com/PoftPuft)

**Projeto original**: [alishahryar1/free-claude-code](https://github.com/alishahryar1/free-claude-code)

**Mantido por**: Comunidade Free Claude Code

---

<div align="center">
  <sub>Feito com ❤️ para a comunidade de desenvolvedores brasileiros</sub>
</div>