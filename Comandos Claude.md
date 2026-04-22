# Comandos Claude Code

## Comandos de Sessão
| Comando | Descrição |
|---|---|
| `/context` | Visualiza uso atual do contexto como um grid colorido |
| `/clear` | Inicia nova sessão com contexto vazio (sessão anterior fica no disco, recuperável com `/resume`) |
| `/compact` | Libera contexto resumindo a conversa atual |
| `/status` | Exibe status do Claude Code: versão, modelo, conta, conectividade e ferramentas |
| `/resume` | Retoma uma sessão anterior salva em disco |
| `/web-setup` | Configura Claude Code na web (requer conta GitHub conectada) |
| `/remote-control` | Conecta o terminal para sessões de controle remoto |

## Agent Teams — Comandos e Configuração

### Habilitar Agent Teams
Arquivo: `~\.claude\settings.json`
```json
{
  "env": {
    "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1"
  }
}
```

### Fluxo de trabalho com times
1. Criar time → `TeamCreate`
2. Criar tarefas → `TaskCreate`
3. Subir agentes → `Agent` (com `team_name` e `name`)
4. Atribuir tarefas → `TaskUpdate` (parâmetro `owner`)
5. Comunicar → `SendMessage` (por nome do agente)
6. Encerrar → `SendMessage` com `{"type": "shutdown_request"}`
7. Deletar time → `TeamDelete`

### Mensagens entre agentes
```
@nome-do-agente    — para falar com um agente específico durante a sessão
SendMessage(to: "nome-do-agente")  — via ferramenta
SendMessage(to: "*")               — broadcast para todos
```

### Status de tarefas
- `pending` → `in_progress` → `completed`
- `deleted` — remove permanentemente

## Referência rápida de ferramentas
| Ferramenta | Uso |
|---|---|
| `TeamCreate` | Cria o time e lista de tarefas |
| `TeamDelete` | Encerra e limpa o time (após shutdown de todos os membros) |
| `TaskCreate` | Cria uma tarefa na lista do time |
| `TaskUpdate` | Atualiza status/dono/dependências de uma tarefa |
| `TaskList` | Lista todas as tarefas do time |
| `TaskGet` | Detalha uma tarefa específica |
| `SendMessage` | Envia mensagem para um ou todos os agentes |
| `Agent` | Sobe um novo agente (com `team_name` para entrar no time) |
