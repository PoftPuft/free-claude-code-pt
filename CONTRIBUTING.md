# Contribuindo

Obrigado por ajudar a melhorar o Free Claude Code. Mantenha as mudanças focadas, teste o comportamento alterado e preserve os fluxos de trabalho públicos do Claude Code e Codex.

## Antes de Abrir um Pull Request

- PRs apenas de documentação são reservados para o proprietário do repositório.
- Inclua atualizações relevantes no README e outra documentação junto com mudanças de código de produção. Essas atualizações acompanhantes não exigem issue separada.
- Não abra pull requests de integração Docker.
- Para bugs, inclua todos os mapeamentos de modelo, o modelo ativo quando a falha ocorreu, o erro completo e passos reproduzíveis.
- Adicione testes focados para mudanças de comportamento e casos de borda relevantes.

## Títulos de Pull Request

Mudanças em `assets/`, `scripts/`, `src/`, `pyproject.toml` ou `uv.lock` exigem título começando com `patch: `, `minor: ` ou `major: ` seguido de uma descrição. Use exatamente um espaço após os dois pontos.

PRs sem mudanças nesses caminhos não devem usar prefixo de release. Não edite números de versão. A publicação calcula a versão após o merge, cria sua tag Git e publica no PyPI e GitHub Releases.

## Configuração de Desenvolvimento

Instale [uv](https://docs.astral.sh/uv/), depois execute diretamente do checkout. O uv instala automaticamente a versão Python requerida pelo projeto.

```bash
git clone https://github.com/PoftPuft/free-claude-code-pt.git
cd free-claude-code-pt
uv run fcc-server
```

Use `uv run` para comandos Python. Não execute o projeto com um interpretador Python global.

## Verificações de Qualidade

Execute a sequência completa de CI local antes de abrir um pull request:

```bash
./scripts/ci.sh
```

```powershell
.\scripts\ci.ps1
```

Flags úteis de iteração: `--only`, `--skip` e `--dry-run` no macOS/Linux, ou `-Only`, `-Skip` e `-DryRun` no PowerShell.

Comandos individuais de reparo e teste:

```bash
uv run ruff format
uv run ruff check --fix
uv run pyrefly check
uv run pytest -v --tb=short
```

Avisos do Pyrefly falham a verificação. GitHub CI roda Ruff em modo check-only e também proíbe `# type: ignore`, `# ty: ignore`, `# pyrefly: ignore` e workarounds legados de anotação. Corrija os problemas de tipagem e limites de importação subjacentes em vez de suprimi-los.

## Padrões do Projeto

- Alvo Python 3.14 e confie em anotações preguiçosas nativas; não adicione `from __future__ import annotations`.
- Python 3.14 suporta múltiplos tipos de exceção sem parênteses, como `except TypeError, ValueError:`.
- Mantenha comportamento compartilhado do protocolo Anthropic sob `src/free_claude_code/core/anthropic/` em vez de importar utilitários de outro provedor.
- Mantenha configuração específica do provedor no provedor que a possui.
- Remova código de compatibilidade morto ao completar migrações, a menos que preservar uma interface publicada seja explicitamente necessário.