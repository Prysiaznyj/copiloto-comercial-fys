# Copiloto Comercial — caso FYS

Versão 0.1, criada em 16/10/2026. Protótipo educacional independente para o desafio DIO; não é um canal oficial da FYS ou do Grupo HEINEKEN.

## Problema e usuário

Vendedores precisam preparar abordagens e continuar negociações com padarias, considerando desconhecimento da marca, experimentação, visibilidade e disponibilidade. O copiloto organiza o contexto, trata objeções e sugere uma próxima mensagem para revisão humana.

## Como experimentar

Veja o [guia por ferramenta](GUIA-DE-USO.md) para ChatGPT, Claude, Gemini, Antigravity, OpenCode e uso portátil em outros ambientes. Para copiar de uma vez, use `INICIAR-COPILOTO.txt`, que reúne o prompt e a base. Esse arquivo é uma cópia gerada: regenere-o quando os três documentos de origem mudarem.

1. Abra uma conversa nova na ferramenta de IA de sua preferência.
2. Cole o conteúdo de `PROMPT.md` e, em seguida, os dois arquivos de `knowledge/`, identificados pelos nomes. Os arquivos não são lidos automaticamente só por existirem nesta pasta.
3. Preencha a entrada abaixo e envie.
4. Confira as sugestões, as fontes e as condições comerciais antes de usar qualquer mensagem.

```text
Estabelecimento: padaria
Etapa: primeira abordagem
Fala do cliente: Nunca ouvi falar de FYS. Aqui o pessoal pede as marcas de sempre.
Objetivo do vendedor: entender se existe abertura para apresentar a marca
Contexto conhecido: ainda não compra FYS
Canal: WhatsApp
Condições comerciais confirmadas: nenhuma
Humor: 2
```

## Arquivos

- `PROMPT.md`: instruções reutilizáveis do copiloto, configuradas para FYS.
- `knowledge/contexto-fys.md`: fatos, limites e referências.
- `knowledge/tom-de-voz.md`: direção de linguagem e exemplos criados para o protótipo.
- `VALIDACAO.md`: cenários para experimentar e critérios de revisão.

## Abordagem e limites

Esta versão funciona por prompt com contexto fornecido na conversa. Não tem integração com estoque, catálogo, CRM ou WhatsApp e não envia mensagens. A base não representa treinamento do modelo. Nenhum resultado comercial foi medido. Há respostas de testes manuais fornecidas pelo usuário e revisadas em [VALIDACAO.md](VALIDACAO.md), com evidências e limitações de configuração registradas. Os nove cenários foram aprovados no conteúdo observado; isso não garante resultados em produção ou em outros modelos.

O humor é parte do produto: autoironia, sarcasmo e acidez sobre a própria marca e os clichês publicitários. A adaptação para revendedores é uma hipótese de design, não uma reprodução de atendimento oficial.

## Origem e créditos

- Contexto FYS e transcrição: https://github.com/digitalinnovationone/copiloto-vendas-ia-atendimento-cliente-fys
- Orientação de aprendizado: https://github.com/digitalinnovationone/dio-agent
- Estrutura de vendas consultivas inspirada nas anotações do exemplo de aula DIO: https://github.com/Prysiaznyj/anotacoes-dio-assistente-vendas-gamer . O prompt gamer original é material de aula; a adaptação FYS foi construída neste projeto com apoio de IA.
- Fontes públicas de comunicação: registradas em `knowledge/contexto-fys.md`.

## Evolução

Validar com cenários e feedback de vendedores; melhorar a base com catálogo e políticas aprovadas; criar interface; separar configuração e conhecimento por empresa. Para outra empresa, revisar também etapas comerciais e critérios de qualificação, além de trocar nome e tom de voz.
