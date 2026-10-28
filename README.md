# Isso é golpe?

Cole uma mensagem suspeita: o site marca os trechos típicos de golpe (regras no navegador) e, se você marcar a opção, pede uma segunda opinião a um modelo do Hugging Face.

## Como rodar
1. Instale o Node 18 ou mais novo.
2. Crie um token em huggingface.co > Settings > Access Tokens (permissão de leitura/inferência).
3. Copie `.env.example` para `.env` e coloque seu token.
4. `npm start` e abra http://localhost:3000

O token fica só no servidor (`server.js`). Nunca envie o `.env` ao GitHub.

## Observações
- Sem token ou sem internet, as marcações por regras continuam funcionando.
- O modelo padrão foi treinado principalmente em inglês; pode errar em português. Troque com `HF_MODEL` no `.env` e ajuste a regex de rótulos em `server.js` (`suspeito`).
- Limite de 1000 caracteres por texto e 10 consultas por minuto por IP.
- É uma ferramenta de apoio, não garante que uma mensagem seja ou não golpe.
