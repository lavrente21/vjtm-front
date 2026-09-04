SISTEMA DE RELATÓRIOS — FRONT-END (pronto para Netlify, ligado ao backend real)
================================================================================

COMO PUBLICAR NO NETLIFY
1. Antes de publicar, abre "index.html" e edita a linha perto do topo do
   <script> que diz:
       const API_BASE_URL = 'https://SEU-BACKEND.onrender.com';
   Troca pelo URL real do teu backend no Render (ver backend/README.md).
2. Entra em https://app.netlify.com
3. "Add new site" -> "Deploy manually"
4. Arrasta esta pasta inteira para a área de upload
5. O Netlify dá-te um link (ex: nome-aleatorio.netlify.app) — é esse link
   que deves colocar como CORS_ORIGIN nas variáveis de ambiente do Render.

ESTE FRONT-END JÁ NÃO USA DADOS LOCAIS
Ao contrário da versão anterior, este já fala a sério com a tua API (Render +
Supabase) — os dados ficam guardados na base de dados real, partilhados por
todas as lojas, com login verdadeiro (JWT) e todas as regras de negócio
aplicadas também do lado do servidor (não só na interface).

LOGIN DE TESTE (definido no schema.sql)
Utilizador: admin
Password: admin123
(vai pedir para trocar a password no primeiro acesso)

ORDEM RECOMENDADA DE DEPLOY
1. Configura o Supabase e corre o schema.sql (ver backend/README.md)
2. Publica o backend no Render, com as variáveis de ambiente certas
3. Edita o API_BASE_URL neste index.html com o link do Render
4. Publica esta pasta no Netlify
5. Volta ao Render e define CORS_ORIGIN com o link do Netlify
