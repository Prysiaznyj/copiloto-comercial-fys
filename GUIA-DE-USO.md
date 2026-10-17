# Como usar o copiloto na ferramenta de sua escolha

Guia consultado em 16/10/2026. Configuração por instruções e contexto; esta versão não exige API, servidor ou instalação de dependências. A ferramenta escolhida precisa estar acessível na sua conta. Recursos, nomes de menus e limites variam por versão e plano.

## O que é um harness?

É o ambiente que organiza a conversa, as instruções, os arquivos e as ferramentas disponíveis para a IA. O modelo produz as respostas; o ambiente define como você fornece contexto e quais ações ele pode executar.

ChatGPT, Claude e Gemini oferecem interfaces de conversa. Antigravity, OpenCode e Codex também permitem trabalhar com arquivos locais. Gemini e Antigravity não são o mesmo aplicativo. Uma assinatura de chat também não deve ser presumida como acesso a API ou a todos os provedores de outra ferramenta.

## Arquivos de que você precisa

- `PROMPT.md`: comportamento e formato das respostas.
- `knowledge/contexto-fys.md`: fatos e referências F1–F4.
- `knowledge/tom-de-voz.md`: linguagem e exemplos adaptados.
- `INICIAR-COPILOTO.txt`: cópia consolidada dos três anteriores para uso por colagem.

Não é necessário carregar os arquivos do DIO Agent para atender como copiloto. O DIO Agent orienta o aprendizado; o prompt FYS orienta a simulação comercial. Misturar os dois papéis pode fazer a ferramenta explicar o exercício em vez de responder ao vendedor.

## 1. ChatGPT — teste imediato em uma conversa comum

1. Abra uma conversa nova no ChatGPT.
2. Abra `INICIAR-COPILOTO.txt` no editor de texto, copie todo o conteúdo e cole na conversa.
3. Envie e aguarde a confirmação de configuração.
4. Envie o cenário de teste ao final deste guia.
5. Confira a resposta com os critérios de `VALIDACAO.md`.

Alternativa: cole `PROMPT.md` como mensagem e anexe os dois arquivos de conhecimento, pedindo que sejam consultados antes da resposta. Se o formato `.md` não for aceito, use cópias `.txt` ou cole o conteúdo identificando o nome de cada arquivo. Anexar somente o prompt como documento pode não comunicar claramente que ele deve orientar o comportamento.

Uma conversa nova exige fornecer o contexto novamente. Um caminho no seu computador ou o link deste repositório, sozinho, não transfere os arquivos para a conversa.

## 2. ChatGPT — configuração reutilizável em Projeto

1. Na área de Projetos, crie um projeto chamado **Copiloto Comercial FYS**.
2. Adicione os dois arquivos de `knowledge/` às fontes/arquivos do projeto.
3. Nas instruções do projeto, cole o conteúdo de `PROMPT.md`.
4. Inicie uma conversa dentro desse projeto e envie o cenário.
5. Ao alterar a versão local, atualize também as instruções e os arquivos enviados.

Se o campo de instruções não comportar o prompt, carregue-o como fonte e coloque no campo: “Para as simulações comerciais, consulte e siga PROMPT.md. Consulte contexto-fys.md e tom-de-voz.md antes de responder. Se não conseguir acessar algum arquivo, informe qual falta.” Verifique esse carregamento no primeiro teste. Um Projeto do ChatGPT não espelha automaticamente a pasta local.

Referência: [Projetos e conversas — documentação OpenAI](https://learn.chatgpt.com/docs/projects).

## 3. Claude — conversa ou Projeto

Para teste rápido, abra uma conversa nova e cole `INICIAR-COPILOTO.txt`; depois envie o cenário.

Para reutilizar, quando Projetos estiver disponível na sua conta:

1. Abra Projects e crie **Copiloto Comercial FYS**.
2. Coloque `PROMPT.md` nas instruções do projeto.
3. Adicione os dois documentos de conhecimento aos arquivos do projeto.
4. Inicie uma conversa nele e envie o cenário.
5. Atualize as cópias quando editar os arquivos locais.

Se houver limite de campo, use o mesmo encaminhamento explícito ao arquivo de prompt descrito no fluxo de Projeto do ChatGPT. Claude no navegador e Claude Code são ambientes distintos; este passo a passo trata da conversa no Claude.

Referência: [Criar e gerenciar projetos — Claude](https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects).

## 4. Gemini — conversa ou Gem

Para teste rápido, cole `INICIAR-COPILOTO.txt` em uma conversa nova.

Para reutilizar:

1. No Gemini pela web, abra a área de Gems e crie um novo Gem.
2. Dê o nome **Copiloto Comercial FYS**.
3. Cole `PROMPT.md` nas instruções.
4. Adicione os dois arquivos de conhecimento na área Knowledge/Conhecimento.
5. Experimente o cenário na prévia e salve o Gem. A prévia não substitui salvar.
6. Abra o Gem salvo para continuar os testes.

Se anexos ou Gems não estiverem disponíveis, use o fluxo por colagem. Não presuma que arquivos locais permanecem sincronizados.

Referência: [Usar Gems — Google](https://support.google.com/gemini/answer/15146780).

## 5. Google Antigravity — pasta local

1. Abra **a pasta `prototipo-copiloto-fys`** como workspace.
2. No painel do agente, peça: “Leia PROMPT.md, knowledge/contexto-fys.md e knowledge/tom-de-voz.md. Nesta conversa, simule o copiloto definido nesses arquivos. Não altere arquivos nem envie mensagens externas.”
3. Confira se os três arquivos foram lidos e envie o cenário.
4. Para persistência, use o painel de Customizations e crie uma regra de workspace com esse encaminhamento e ativação contínua. Evite regras globais para um personagem específico deste projeto.
5. Em uma conversa nova, confirme novamente o acesso à base antes de testar.

As regras do ambiente não substituem o conteúdo dos arquivos referenciados: peça explicitamente sua leitura. Nesta versão não instalamos regras locais nem modificamos configurações da sua ferramenta.

Referência: [Rules — Antigravity](https://antigravity.google/docs/rules/).

## 6. OpenCode — pasta local

Com o OpenCode instalado e um provedor/modelo configurado:

1. Abra o terminal na pasta `prototipo-copiloto-fys` e inicie `opencode`.
2. Peça a leitura dos mesmos três arquivos e a simulação, usando a mensagem do fluxo Antigravity.
3. Envie o cenário; não é preciso instalar pacotes deste protótipo.
4. Para persistir instruções, crie nessa pasta um `AGENTS.md` com o encaminhamento de leitura, ou configure os arquivos em `instructions` no `opencode.json`.
5. Não substitua um arquivo de configuração existente sem incorporar suas regras anteriores. Referências em AGENTS.md não são automaticamente expandidas: instrua o agente a ler os arquivos.

Referência: [Rules — OpenCode](https://docs.opencode.ai/docs/rules/).

## Outras ferramentas, inclusive Codex

O fluxo portátil é: abrir a pasta no ambiente com acesso local, pedir explicitamente a leitura dos três documentos e enviar o cenário. Em interfaces sem acesso local, cole o arquivo consolidado. No Codex CLI, a documentação permite iniciar no diretório do projeto; confira o contexto e as regras aplicáveis antes de simular.

Este guia não cria um `AGENTS.md` de personagem na pasta do protótipo: isso poderia confundir futuras tarefas de desenvolvimento com o papel comercial. A pessoa escolhe se deseja persistir essa configuração na ferramenta.

Referência: [Projetos e diretório de trabalho — OpenAI](https://learn.chatgpt.com/docs/projects).

## Cenário para copiar após configurar

```text
Estabelecimento: padaria de bairro
Etapa: primeira conversa
Fala do cliente: Nunca ouvi falar de FYS. Minha geladeira já está cheia e não quero produto parado.
Objetivo do vendedor: entender se existe abertura para apresentar a marca
Contexto conhecido: ainda não compra FYS
Canal: WhatsApp
Condições comerciais confirmadas: nenhuma
Humor: 2

Responda como o copiloto, nas seções A–G. Na seção F, identifique os fundamentos da base e as sugestões criadas para o cenário.
```

Procure uma mensagem útil, com autoironia curta e uma pergunta principal. Não há uma redação única correta. Experimente depois uma reclamação de entrega: o humor deve cair para 0, sem prazo ou solução inventados.

## Como comparar e registrar

Use a mesma versão dos arquivos e a mesma entrada em cada ferramenta. Registre data, ferramenta, modelo quando visível, resposta e avaliação em `VALIDACAO.md`. Não afirme que uma ferramenta foi validada apenas porque a configuração está documentada. Até este momento, estes fluxos foram conferidos com documentação, sem teste prático nas contas das plataformas.

Se a resposta ignorar o tom, peça revisão com `tom-de-voz.md`. Se inventar condições, registre a falha e revise o prompt. Se não conseguir citar F1–F4 corretamente, verifique se a base foi carregada. Arquivos enviados não se atualizam automaticamente quando você edita a versão local.

## Configuração por contexto e integração por API

Os fluxos acima permitem testar o protótipo manualmente. Uma integração com interface própria, CRM, estoque ou mensageria seria outra etapa, com backend, autenticação e uso de APIs. Configurar um Projeto ou Gem não conecta o copiloto ao WhatsApp nem o faz atender clientes automaticamente.
