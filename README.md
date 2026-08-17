# Diário de Corte

App de registro semanal de peso, calorias, passos e treinos (PPL/UL), com cálculo de déficit/superávit.

## Como colocar no ar (GitHub Pages)

1. Crie um repositório novo no GitHub (pode ser privado ou público — se for privado, o GitHub Pages exige plano pago; se não tiver certeza, use público).
2. Faça upload de todos os arquivos desta pasta (`index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`) para a raiz do repositório.
3. No repositório, vá em **Settings → Pages**.
4. Em "Source", selecione a branch `main` (ou `master`) e a pasta `/ (root)`. Salve.
5. Em alguns minutos, o GitHub vai te dar uma URL do tipo:
   `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`
6. Abra essa URL no celular.

## Instalar como app no celular

- **iPhone (Safari):** abra a URL → toque no ícone de compartilhar → "Adicionar à Tela de Início".
- **Android (Chrome):** abra a URL → menu de três pontinhos → "Adicionar à tela inicial" (ou vai aparecer um banner automático de instalação, já que o app tem manifest + service worker).

Depois de instalado, ele abre em tela cheia, com ícone próprio, e funciona **offline** (o service worker guarda uma cópia local do app).

## Importante sobre os dados

Essa versão salva os dados no **localStorage do navegador**, não mais na nuvem do Claude. Isso significa:

- Os dados ficam **só nesse navegador/dispositivo específico**. Se você instalar em outro celular ou trocar de navegador, começa vazio.
- Limpar dados de navegação/cache do navegador **apaga o histórico salvo**. Evite usar o modo anônimo/privado.
- Não há sincronização automática entre dispositivos.

Se no futuro você quiser sincronizar entre vários aparelhos, o próximo passo seria adicionar um backend simples (ex: Firebase, Supabase) para guardar os dados na nuvem — isso exigiria mudanças adicionais no código.

## Estrutura dos arquivos

- `index.html` — o app inteiro (interface + lógica).
- `manifest.json` — metadados do PWA (nome, ícone, cor do tema).
- `sw.js` — service worker, permite funcionamento offline.
- `icon-192.png`, `icon-512.png` — ícones do app.
