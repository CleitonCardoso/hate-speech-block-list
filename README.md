# hate-speech-block-list

Lista assinada usada pela extensão Blocklist Runner.

- `lista.json`: a lista.
- `lista.json.sig`: assinatura Ed25519 de `lista.json`. A extensão recusa a lista se a assinatura não bater.

Endereço para colar na extensão:

```
https://raw.githubusercontent.com/CleitonCardoso/hate-speech-block-list/main/lista.json
```

## Critérios

Lista de teste, mantida pelo dono do repositório para validar o fluxo de bloqueio. Não é uma classificação das pessoas listadas.

## Atualizar

1. Edite `lista.json` e aumente `version`.
2. Assine (a chave privada fica fora do repositório):
   `corepack pnpm exec tsx scripts/sign-list.ts <caminho>/lista.json ~/.blocklist-runner/list-signing.key`
3. Faça commit de `lista.json` e `lista.json.sig` juntos.
