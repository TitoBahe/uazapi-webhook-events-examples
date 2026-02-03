# Webhook Events Examples

Este diretório contém exemplos de eventos de webhook enviados pela API UAZAPI.

## Estrutura de Pastas

```
webhook-events-examples/
├── connection/
│   ├── connected.event.json      # Evento quando a instância conecta
│   └── connecting.event.json     # Evento quando a instância está conectando (QR Code)
│
└── messages/
    ├── group-chat/              # Mensagens de grupos
    │   ├── from-me/             # Mensagens enviadas pela instância conectada
    │   └── from-others/         # Mensagens recebidas de outros participantes
    │
    └── user-chat/               # Mensagens de conversas individuais
        ├── from-me/             # Mensagens enviadas pela instância conectada
        └── from-others/         # Mensagens recebidas de outros usuários
```

## Tipos de Mensagens

Cada pasta contém exemplos de diferentes tipos de mensagens:

- `audio.sent.json` - Mensagem de áudio
- `contact.sent.json` - Contato compartilhado
- `emoji.sent.json` - Emoji
- `file.sent.json` - Arquivo
- `gif.sent.json` - GIF
- `image.sent.json` - Imagem
- `location.sent.json` - Localização
- `poll.sent.json` - Enquete criada
- `poll.vote.me.json` - Voto na enquete pela pessoa que criou a enquete
- `poll.vote.other.json` - Voto na enquete por outra pessoa (número diferente)
- `reaction.sent.json` - Reação a uma mensagem
- `sticker.sent.json` - Sticker
- `text.edited.json` - Texto editado
- `text.sent.json` - Texto enviado
- `video.sent.json` - Vídeo

## Sobre Polls (Enquetes)

### `poll.vote.me.json`
Este evento é disparado quando a **pessoa conectada a instância** vota nela. Isso acontece independentemente de ser o mesmo número conectado à instância ou não. Ou seja, se você criou uma enquete e depois votou nela, este evento será disparado.

### `poll.vote.other.json`
Este evento é disparado quando **outra pessoa com um número diferente** vota na enquete. Apenas votos de outros participantes (não o criador da enquete) geram este tipo de evento.

## Notas Importantes

- Todos os valores sensíveis (tokens, lids, BaseUrl, instanceName) foram substituídos por valores genéricos para fins de exemplo
- Os arquivos `.json` contêm JSON formatado com exemplos reais de eventos
- Cada arquivo representa um único evento de webhook
