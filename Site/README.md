# SGRDigital — Landing Page

Site estático (HTML/CSS/JS puro, sem build), pronto para o Cloudflare Pages.

## Estrutura

```
sgrdigital/
├── index.html      ← site completo (CONFIG no topo)
├── _headers        ← cabeçalhos de segurança e cache (Cloudflare)
├── logo-dark.png   ← (opcional) seu logo oficial
└── projetos/       ← (opcional) prints do portfólio
```

## Editando

Abra `index.html` e altere a constante `CONFIG` logo no início:

- `whatsapp.numero`: DDI + DDD + número, só dígitos (ex: `5511987654321`)
- `whatsapp.mensagem`: texto que já vem escrito ao abrir o WhatsApp
- `email`, `cnpj`, `cidade`, `redes`
- `logo`: troque `null` por `"/logo-dark.png"` depois de colocar o arquivo na pasta
- `projetos`: preencha `imagem` (ex: `"/projetos/gelo.webp"`) e `link` de cada projeto

Para os prints, use imagens de ~1600×1100 px em `.webp`.

## Publicando (GitHub + Cloudflare Pages)

1. Crie um repositório no GitHub (ex: `sgrdigital-site`) e envie estes arquivos.
2. No painel da Cloudflare: **Workers & Pages → Create → Pages → Connect to Git**.
3. Escolha o repositório. Em *Build settings*: Framework **None**, build command **vazio**, output directory **/**.
4. Clique em **Save and Deploy**. O site sai em `sgrdigital-site.pages.dev`.
5. Em **Custom domains**, adicione `sgrdigital.com.br`.

Cada `git push` publica uma nova versão automaticamente.

## Supabase

Não é necessário nesta versão: o contato vai direto para WhatsApp e e-mail.
Ele passa a fazer sentido se você quiser um formulário que salve os leads num banco.
