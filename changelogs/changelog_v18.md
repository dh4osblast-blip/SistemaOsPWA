# MicroLab OS v18 — Versão personalizável (base: v17, arquivo único)

## Novo
- **Personalização** (Ajustes > Personalização do negócio): nome, frase abaixo do nome, cidade, WhatsApp, Instagram, frase de chamada (opcional) e **cor principal**. Salva em `cfg.empresa`.
- **Assistente do primeiro acesso** (só Administrador): nome, contatos, cor, Pix, horas de bancada, quanto quer ganhar por mês e hora técnica mínima. Dá para pular e reabrir em Ajustes.
- **Logo**: sem logo enviada, aparece um quadrado com as iniciais do nome, na cor escolhida. Enviar uma logo continua igual.
- A cor muda botões, menu, agenda, painel da fonte e tela inicial. Cores muito claras são recusadas (o texto branco sumiria).

## Removido (dados pessoais e marca fixa)
- Logos, favicon e avatar embutidos da MicroLab.
- WhatsApp e Instagram fixos na impressão da OS, no laudo da fonte e nas mensagens (orçamento, venda, compra, aniversário, clientes inativos). Agora usam os dados de quem configurou; contato vazio não é impresso.
- Nome e cidade do Pix (padrões "MICROLAB" e "SALVADOR"), "Salvador" no catálogo, frase "Orçamento antes do serviço." (virou campo opcional).
- Nome do app e do arquivo de backup: neutros (`backup-assistencia-AAAA-MM-DD.json`).

## Dados existentes
- Nada é apagado. `migrar()` só acrescenta `cfg.empresa`; quem já tem OS ou clientes não vê o assistente.

## Arquivos
`index.html`, `sw.js` (cache `microlab-os-v18`), `manifest.webmanifest` (nome neutro), `icon-192.png` e `icon-512.png` (ícone neutro: celular com engrenagem).

## Testado (navegador simulado, jsdom)
Primeiro acesso, assistente, salvar marca, cor aplicada, 20 telas sem erro e sem marca antiga, impressão A4, mensagem de WhatsApp, Pix com dados do usuário, contato vazio, cor clara recusada, migração idempotente, dados antigos.
## Não testado
Celular real, Brave/Android, impressão física, instalação do PWA, sincronização na nuvem e fonte ZK-SK150C conectada.

## Limites conhecidos
- O nome do app instalado vem do `manifest.webmanifest` ("Assistência") e é igual para todos; cada pessoa pode renomear o atalho no celular. Ícone neutro igual para todos.
- Textos de garantia e condições são modelos; revisar com profissional.
