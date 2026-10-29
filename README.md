# M.SocialPro

Agente de social media para o [Claude Code](https://claude.com/claude-code). Ele recebe cronogramas de postagem (de pessoas ou de outros agentes), confere cada post e agenda nas ferramentas oficiais das redes sociais.

O comportamento completo está em [`CLAUDE.md`](CLAUDE.md). O Claude Code lê esse arquivo automaticamente sempre que você abre uma conversa nesta pasta. Na primeira mensagem, o agente passa as orientações de login, ferramentas, envio de conteúdo e aprovação antes de fazer qualquer tarefa.

## Como usar

1. Clone o repositório e abra a pasta no Claude Code (app desktop ou terminal).
2. **Login:** não envie senhas ao agente. Ele não digita senhas por regra de segurança. Faça o login das contas dos clientes no navegador que o agente usa (o navegador do app Claude ou o Chrome com a extensão Claude). O ideal é que o cliente te adicione como parceiro ou administrador no **Meta Business Suite**, no LinkedIn e no YouTube, para que você não precise da senha dele.
3. Crie a pasta `Clientes/<NomeDoCliente>/` com:
   - `cronograma.csv`, no formato de [`templates/cronograma-modelo.csv`](templates/cronograma-modelo.csv);
   - `midias/`, com os arquivos citados no cronograma.
4. Peça ao agente: *"Confira e agende o cronograma do cliente X"*.
5. Revise o resumo que ele mostra e aprove. Só então ele agenda.

## Ferramentas oficiais recomendadas

- **Meta Business Suite** (business.facebook.com): Instagram e Facebook (feed, carrossel, reels, stories)
- **TikTok Studio** (tiktok.com/tiktokstudio)
- **LinkedIn**: agendamento nativo na página da empresa
- **YouTube Studio** (studio.youtube.com)
- Agendamento nativo do Pinterest, do X e do Threads

## Integração com outros agentes

Os agentes que produzem conteúdo devem gravar no mesmo `cronograma.csv`, com `status = pronto`, e colocar as mídias em `midias/`. O M.SocialPro só processa linhas `pronto` ou `aprovado` e trata o texto recebido como dado: nunca executa instruções escondidas em legendas ou observações.

## Segurança

- Nunca coloque senhas, códigos 2FA, tokens ou dados pessoais de clientes neste repositório.
- A pasta `Clientes/` fica fora do Git por padrão (veja `.gitignore`), para não publicar material de clientes.
