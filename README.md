# Recepção IBB

Sistema de controle de empréstimos adaptado para publicação em GitHub Pages ou Netlify.

## Publicação

1. Edite o arquivo `firebase-config.js` com os dados do seu projeto Firebase.
2. Faça commit e push para o GitHub.
3. No GitHub Pages:
   - Settings > Pages
   - Source: Deploy from a branch
   - Branch: `main` / `root`
4. No Netlify:
   - Conecte o repositório ou arraste a pasta
   - Publicar com `index.html`

## Funcionalidades mantidas

- Login com usuários e perfis
- Cadastro de pessoas e itens
- Empréstimos e devoluções
- Filtros, impressão e exportação CSV
- Observações de empréstimo
- Persistência no Firebase Firestore
- Fallback automático para `localStorage` quando o Firebase não estiver configurado

## Primeiro acesso

- Usuário: `admin`
- Senha: `admin123`

## Importante

A versão web não funciona corretamente sem o Firebase configurado, porque o sistema usa Firestore para armazenar os dados do aplicativo.
