# Criar agentes para auxílio de busca de emprego

## Objetivo
Criar um time de agentes para analisar o currículo do Roger Tang e buscar vagas de coordenação/gestão hands-on.

## Agentes criados
- Especialista em currículos
- Chefe que vai coordenar todos e que será um revisor
- Recrutador Sênior
- Recrutador Júnior
- Especialista em Busca de vagas no LinkedIn. Vagas de coordenação ou gestão "hands on"

## Habilitar o Claude Agents Teams
Arquivo: `~\.claude\settings.json`
```json
{
  "env": {
    "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1"
  }
}
```

## Prompt para criar os agentes
```
Crie um time de agentes com 5 agentes.
1) Chefe que vai coordenar todos e que será um revisor do trabalho geral
2) Especialista em currículos
3) Recrutador Sênior que irá interpretar o currículo de acordo com sua função
4) Recrutador Júnior que irá interpretar o currículo de acordo com sua função
5) Especialista em Busca vagas do meu perfil no linkedin. Gostaria de vagas de coordenação ou gestão "hands on"
```

## Output — Time criado em 21/04/2026

| # | Agente | Função | Status |
|---|---|---|---|
| 1 | coordenador-chefe | Coordena, revisa e consolida tudo | Concluído |
| 2 | especialista-curriculos | Análise técnica do currículo | Concluído (Task #1) |
| 3 | recrutador-senior | Visão de recrutador experiente | Concluído (Task #2) |
| 4 | recrutador-junior | Visão de triagem inicial | Concluído (Task #3) |
| 5 | especialista-vagas | Busca de vagas no LinkedIn e portais | Concluído (Task #4) |

## Resultado
Relatório consolidado salvo em: `Relatorio_Final_Time_Agentes.md`

## Para falar com agentes específicos (durante execução)
```
@coordenador-chefe
@especialista-curriculos
@especialista-vagas
@recrutador-junior
@recrutador-senior
```

## Próximos passos
- [ ] Reescrever currículo com base nas recomendações do relatório
- [ ] Atualizar LinkedIn
- [ ] Configurar alertas de vagas
