# Recepção IBB

Sistema de controle de empréstimos de chaves, controles e equipamentos da recepção da IBB.
Site estático publicado no GitHub Pages, com login e banco de dados no Firebase.

## Como funciona

- **Login:** Firebase Authentication (e-mail e senha).
- **Dados:** Cloud Firestore, projeto `recepcaoibb-efe73`, região São Paulo (`southamerica-east1`).
- **Atualização em tempo real:** o que uma recepcionista registra aparece na hora para as outras.
- **Segurança:** só quem tem login **e** um perfil ativo na coleção `users` acessa os dados
  (veja `firestore.rules`). Só Admin cria/edita usuários e altera a hora do sistema.
- **Plano:** Spark (gratuito, sem cartão). O Storage não está ativado porque o app não envia arquivos.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | O app inteiro |
| `firebase-config.js` | Identificação pública do projeto Firebase (pode ficar no repositório; a proteção vem das regras) |
| `firestore.rules` | Cópia das regras de segurança publicadas no console do Firebase |

## Usuários

- **Novo usuário:** entre como Admin → Configurações → "Novo usuário". Informe nome, e-mail, senha inicial e perfil.
- **Trocar senha:** Configurações → Editar → "Enviar link de nova senha" (o usuário recebe um e-mail),
  ou o próprio usuário clica em "Esqueci minha senha" na tela de login.
- **Bloquear acesso:** Configurações → Inativar. O usuário perde o acesso aos dados na hora.
- **Primeiro administrador:** foi criado no console do Firebase (Authentication → Usuários) e liberado
  com um documento em `users/{UID}` contendo `nome`, `login` (e-mail), `perfil: "Admin"` e `ativo: 1`.

## Publicação (GitHub Pages)

Settings → Pages → Source: *Deploy from a branch* → Branch `main` / `(root)`.
Endereço: https://ibbsupervisao-bot.github.io/RecepcaoIBB/

Para alterar as regras do banco: edite `firestore.rules` e cole o conteúdo em
Firebase Console → Firestore → Regras → Publicar.
