# ⚡ BlipHub Helper

Uma suíte completa de ferramentas para desenvolvedores da plataforma **Blip (Take Blip)**. Permite injetar eventos analíticos (trackings) customizáveis em bots exportados e gerar payloads interativos para WhatsApp de forma 100% client-side (no próprio navegador, sem envio de dados para servidores externos).

🔗 **Acesse online:** [https://pedrohl19.github.io/BlipHub-Helper/](https://pedrohl19.github.io/BlipHub-Helper/)

![GitHub Pages Ready](https://img.shields.io/badge/GitHub%20Pages-Online-brightgreen)
![Client-Side Only](https://img.shields.io/badge/100%25-Client--Side-blue)
![Take Blip](https://img.shields.io/badge/Take-Blip-00A3FF)

---

## 🚀 Ferramentas Incluídas

### 1. 🎯 Bot Tracking Transformer (Injetor Granular de Trackings)
Transforme o arquivo `bot.json` exportado do Blip Builder escolhendo exatamente quais métricas e eventos você quer registrar:
- **Entrada do Bloco**: Registra o acesso ao bloco (`{{block.$title}}` / `{{contact.identity}}`).
- **Saída com Input**: Registra o conteúdo digitado na saída (`{{block.$title}} Conteudo`).
- **Exibição de Mensagens**: Registra `exibicao|{{state.name}}` apenas nos blocos com envio de mensagens ativas.
- **Input Recebido**: Registra `input|{{state.name}}` com o extra `input` preenchido.
- **Validação de Sugestões / Menus**: Injeta script `treat input` com eventos de `selecao` e `inesperado`.
- **APIs HTTP (Entrada & Saída)**: Registra ID GUID único de correlação, método, URL, payload, status HTTP e resposta para cada `ProcessHttp`.
- **Interação Global**: Registra na saída das Ações Globais o histórico completo de transição de blocos, IDs e variáveis de contato.
- **Opções Avançadas**:
  - *Evitar duplicidade*: Limpa trackings injetados anteriormente se o bot for processado mais de uma vez.
  - *Omitir Payload de APIs*: Previne gravação de dados sensíveis ou payloads muito grandes nos extras do Blip.
  - *Atalhos (Presets)*: Completo, Apenas APIs, Apenas Navegação de Blocos ou Limpar.

### 2. 📋 Gerador de Menu Interativo (WhatsApp List Message)
- Criação dinâmica de menus com cabeçalho, corpo, rodapé e botão de ação.
- Suporte a múltiplas seções e múltiplos itens por seção.
- **Controle de IDs Únicos**: Prevenção em tempo real e desduplicação automática de IDs para garantir que o WhatsApp não rejeite a mensagem interativa.
- Prévia ao vivo estilo WhatsApp.
- Botão para copiar o JSON pronto para o componente de **Conteúdo Dinâmico** do Blip.

### 3. 🔗 Gerador de Botão com Link (CTA URL)
- Cria botões de link externo para WhatsApp (`interactive: cta_url`).
- Prévia em tempo real com balão WhatsApp e botão com ícone de link externo.
- Cópia do JSON formatado com 1 clique.

### 4. 👤 Gerador de Contato Dinâmico (vCard)
- Criação do payload de cartão de contato telefônico do WhatsApp (`type: contacts`).
- Campos de primeiro nome, sobrenome, nome formatado, telefone e WhatsApp ID.
- Prévia visual do card de contato.

### 5. ⏱️ Configurador de Horário de Atendimento (Service Hours)
- Grade semanal visual (Domingo a Sábado) com suporte a múltiplos turnos diários.
- Botão rápido para preencher automaticamente de Segunda a Sexta (08h às 18h).
- Importação e exportação de JSON de horários para scripts de atendimento no Blip.

---

## 🔒 Segurança e Privacidade

- **Zero backend**: Todo o processamento de fluxo, regex e montagem de JSON ocorre diretamente na engine JavaScript do seu navegador.
- **Nenhum dado trafega para a nuvem**: Credenciais, tokens e fluxos do Blip permanecem 100% seguros na sua máquina.
