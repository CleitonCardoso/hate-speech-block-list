# hate-speech-block-list

Lista assinada usada pela extensão Blocklist Runner.

- `lista.json`: a lista.
- `lista.json.sig`: assinatura Ed25519 de `lista.json`. A extensão recusa a lista se a assinatura não bater.

Endereço para colar na extensão:

```
https://raw.githubusercontent.com/CleitonCardoso/hate-speech-block-list/main/lista.json
```

## Critérios

Cada pessoa da lista atende aos três critérios abaixo:

1. **Figura pública**: ocupa ou ocupou cargo público, dirige partido, ou tem a comunicação política como atividade pública (comunicadores, artistas que fizeram campanha). Nenhuma pessoa comum.
2. **Apoio público declarado** a Jair Bolsonaro ou à candidatura de Flávio Bolsonaro, com uma fonte pública em `reasonUrl` (notícia ou declaração da própria pessoa). Filiação partidária sozinha não basta.
3. **Conta conferida**: cada perfil foi aberto em 29/10/2026 e o nome exibido bate com a pessoa. Contas de fãs, de apoio, paródias e contas inexistentes foram descartadas.

A categoria `apoio-declarado-bolsonaro` descreve apoio político público, e só isso. Ela não afirma nada sobre a conduta pessoal de ninguém.

## Correções

Se uma conta estiver errada ou uma pessoa não atender aos critérios, abra uma issue com a fonte. A entrada é revista e, se for o caso, removida na versão seguinte.

## Atualizar

1. Edite `lista.json` e aumente `version`.
2. Assine (a chave privada fica fora do repositório):
   `corepack pnpm exec tsx scripts/sign-list.ts <caminho>/lista.json ~/.blocklist-runner/list-signing.key`
3. Faça commit de `lista.json` e `lista.json.sig` juntos.
