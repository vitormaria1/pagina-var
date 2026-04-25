# 🚀 Claude Code Workspace Setup

Template reutilizável com MCPs, hooks e configurações otimizadas para produtividade.

## ✅ O que está configurado

### MCPs (Model Context Protocol)
Três integrações principais já conectadas:
- **chrome-devtools** — Debug e automação do Chrome/DevTools
- **cloudflare-api** — Acesso às APIs do Cloudflare (2500+ endpoints)
- **supabase** — Integração com banco de dados Supabase

### Hooks Personalizados
- 🔔 **Notificação sonora ao terminar** — "Terminei, porra!" toca quando você sai da janela

### Estrutura `.claude/`
```
.claude/
├── settings.json          # Configurações do projeto (MCPs allowlist)
├── settings.local.json    # Overrides locais (não commitado)
└── .mcp.json             # Config dos MCPs com autenticação
```

## 🔧 Como usar em novo projeto

### 1. Duplicar esta pasta
```bash
cp -r /Users/vitormaria/Desktop/workspace ~/novo-projeto
cd ~/novo-projeto
```

### 2. Reconfigurar tokens (IMPORTANTE)
Os tokens do Cloudflare e Supabase precisam ser adicionados localmente:

```bash
# Obter tokens e adicionar via CLI
claude mcp add cloudflare-api https://mcp.cloudflare.com/mcp
claude mcp add supabase https://mcp.supabase.com/mcp
```

Ou editar `.claude/.mcp.json` manualmente com seus tokens.

### 3. Limpar histórico (opcional)
```bash
rm -rf ~/.claude/projects/*/history.jsonl  # Remove histórico de outras sessões
rm -rf ~/.claude/file-history/             # Remove histórico de arquivos
```

## 📋 Checklist ao iniciar novo projeto

- [ ] Duplicar workspace
- [ ] Atualizar tokens dos MCPs
- [ ] Rodar `claude` para verificar MCPs conectados
- [ ] Atualizar `README.md` ou nome do projeto
- [ ] `.gitignore` já está configurado para não publicar `.env.local`

## 🔐 Segurança

- ✅ `.env.local` está no `.gitignore` — tokens locais seguros
- ✅ `.mcp.json` não é commitado — credenciais privadas
- ✅ `settings.local.json` é local — preferências pessoais

## 🎯 Funcionalidades prontas

| Feature | Arquivo | Customização |
|---------|---------|--------------|
| MCPs | `.claude/.mcp.json` | Adicionar/remover servers |
| Notificação sonora | `.claude/settings.json` (hook Stop) | Editar frase em `say 'Terminei, porra!'` |
| Permissões | `.claude/settings.json` | allowedMcpServers array |

## 📝 Próximos passos

1. Testar os MCPs: `claude` → clicar no ícone de MCPs (canto inferior)
2. Verificar se som toca quando terminar uma tarefa
3. Customizar hooks conforme necessário

---

**Template criado em:** 2026-04-21  
**Última atualização:** Quando você duplicar
