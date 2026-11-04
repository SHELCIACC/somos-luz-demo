# Somos Luz — pacote da demo para continuar noutra conta Claude

Este pacote contém a demo clicável da app **Somos Luz** (acompanhamento das sessões do Manual de Mentoria Escolar «Somos Luz») com todas as alterações propostas, pronta a publicar no Vercel.

## Como usar (para quem recebe)

1. Abrir uma conversa nova no Claude e anexar o ficheiro `somos-luz-pacote.zip` inteiro.
2. Escrever, por exemplo: «Lê o LEIA-ME-CLAUDE.md e ajuda-me a publicar esta demo no Vercel» ou «… continua a melhorar a app a partir daqui».

## O que está no pacote

| Ficheiro | Para que serve |
|---|---|
| `index.html` | A demo completa, num só ficheiro (HTML + CSS + JavaScript, sem build). |
| `vercel.json` | Configuração mínima para o Vercel (site estático). |
| `README.md` | Passos curtos de publicação. |
| `Somos_Luz_Proposta_App.pptx` | Apresentação com todas as alterações e o antes/depois. |
| `LEIA-ME-CLAUDE.md` | Este ficheiro: contexto e decisões tomadas. |

## Publicar no Vercel

- **Com o Vercel CLI**: dentro da pasta, `npx vercel --prod`.
- **Pelo site**: subir a pasta para um repositório GitHub e importar em vercel.com/new. Framework Preset: **Other**. Build Command: vazio. Output Directory: `.`.
- A app original do developer está em `somos-luz-five.vercel.app`; esta demo deve ficar num projeto separado (por exemplo `somos-luz-demo`) para não substituir a original.

## Contexto

- **Utilizadora**: revê a app e dá feedback ao developer. A demo serve para mostrar as alterações à Mafalda e ao developer.
- **Público da app**: Professores Coordenadores do Programa de Mentoria Escolar, muitos com pouca literacia digital.
- **Escola de exemplo**: EPC de Búzi, Professor Coordenador «Carlos Mabunda». Os nomes de mentores e mentorandos vêm do vídeo da app original; alguns mentorandos foram acrescentados para chegar a 43.
- **Dados ilustrativos**: os valores das outras escolas, da média nacional, dos rankings e dos indicadores são de exemplo. Na app real têm de vir dos dados do programa.
- A demo guarda o estado só na memória: ao recarregar a página, tudo volta ao início.

## Princípios de desenho (pouca literacia digital)

1. Um número grande por caixa, com uma palavra que o explica.
2. Cores com significado fixo: verde = bem, vermelho = agir, cinzento = referência/média.
3. Cada caixa acaba num botão grande com verbo.
4. Indicadores sem dados não aparecem.
5. A próxima acção está sempre no topo do Início.
6. Letra mínima 15 px, botões de 44–48 px.

## Identidade (do Manual Somos Luz)

- Verde da capa (mais claro no topo da app): `#9bc97a`.
- Cores por etapa: Etapa 1 «Somos Luz!» amarelo `#fedd16` · Etapa 2 «Iluminamos o Nosso Futuro» verde `#00a651` · Etapa 3 «Iluminamos o Nosso Caminho» azul `#01adee` · Etapa 4 «Iluminamos a Nossa Escola» roxo `#91278e`.
- Círculo de Mentorandos: laranja `#ed7d30`. Ferramentas: cinzento-escuro `#58585a`.
- 5 lâmpadas: 1 entregue no início do Jogo + 1 no fim de cada etapa; o filamento tem a cor da etapa.
- 28 sessões em 4 etapas (2, 10, 10, 6); sessões alternadas das Duplas e do Círculo; Círculo de 10 Mentorandos (5 raparigas e 5 rapazes); encontros de 15 em 15 dias.
- Termos: usar só **Mentores** e **Mentorandos** (não «Mentoras e Mentores»), **Dupla**, **Círculo**.
- Fonte: Figtree em toda a app; Fira Sans só na caixa da sessão (bandeirola + rótulo). Notas em caixa tracejada com ícone de megafone.

## Todas as alterações (por ecrã)

### Início
- No topo, alerta fino **«Por fazer agora»**: bandeirola da etapa, sessão a registar e botão «Registar presenças» (sem data, duração nem tipo de sessão).
- **Assiduidade**: média dos últimos 5 Círculos, com «Boa» (≥80%), «Atenção» (60–79%) ou «Baixa» (<60%), barras por sessão e aviso quando uma sessão cai abaixo de 60%. Botão «Ver detalhes».
- **Na nossa escola**: Mentores e Mentorandos com **metas editáveis** (botão «Editar metas»). Verde quando a meta foi atingida ou ultrapassada, vermelho quando está abaixo; sem barras.
- **Desistências**: Mentores e depois Mentorandos (mesma ordem de «Na nossa escola»).
- **Atenção especial**: 3 números (Por resolver a vermelho; Encaminhados e Resolvidos a cinzento), sem gráfico. Botão «Ver os casos».
- **Percurso**: 5 lâmpadas e barra por etapa.
- **A escola vs. outras escolas**: tabela simples com participação média (todas as sessões do Círculo feitas) e desistências; nossa escola a verde se igual ou melhor do que a média, vermelho se pior.
- **Indicadores do programa**: Progressão escolar, **Literacia** (em vez de «Aprendizagem»), Orientação vocacional e competências socioemocionais, Cidadania activa — escola vs. média nacional. Botão «Ver indicadores em detalhe».

### Indicadores em detalhe
- Filtros: Indicador e Ano (2026, 2025).
- Completude do programa.
- Por indicador: a tua escola vs. média nacional (barras), diferença em pontos, lugar no ranking nacional e Top 5 escolas; fora do Top 5 aparece «… 103 Tua escola» a vermelho.

### Registar presenças
- Por dupla: primeiro os **Mentores** só com «Veio / Faltou» (sem perguntas de avaliação).
- Depois os **Mentorandos** (sessões do Círculo): lista com visto, como a ficha do manual (√ presente · X faltou). Todos começam presentes; botão «Todos vieram».
- «Guardar presenças» sempre disponível. Ao guardar, a sessão fica concluída e a seguinte passa a «A decorrer»; a assiduidade é recalculada.

### Situação de risco (em vez de «Atenção especial» no registo)
- Triângulo ao lado de cada nome / botão «Situação de risco a reportar (se houver)».
- Janela com: categorias (Falta muitas vezes, Pode deixar a escola, Gravidez ou união prematura, Problema de saúde, Violência ou maus-tratos, Problemas em casa, Dificuldade em ler ou escrever, Triste ou isolado/a, Outra situação), urgência («Pode esperar pela coordenação» / «Urgente — avisar hoje»), nota opcional e aviso de confidencialidade.
- Ao guardar, cada situação entra em **Casos → Por resolver**.

### Casos (Atenção especial)
- Separadores Por resolver / Encaminhados / Resolvidos.
- Encaminhar (diretora pedagógica, enfermeira do centro de saúde, família, equipa de coordenação) com nota; Resolver com nota.

### Participantes
- Separadores na ordem **Duplas · Mentores · Mentorandos**, cada um com cor clara (verde, amarelo, laranja); abre em Duplas.
- Aviso quando um Círculo não tem 10 Mentorandos.
- **Ficha de inscrição** (Mentor ou Mentorando): nome, turma, F/M, **data de nascimento** (idade calculada automaticamente), dupla, **nome do encarregado** (obrigatório), **contacto do encarregado** (opcional), **«Está em situação de deslocamento?» Sim/Não** — se Sim: «Comunidade de acolhimento» ou «Deslocado/a forçado/a» e **«De onde é deslocado/a?»** —, **problema de saúde** (opcional).
- Mudar de dupla, registar desistência com motivo, criar dupla e alterar mentores.

### Sessões, Guia e Recursos
- Sessões por etapa, com cor e bandeirola; cada sessão indica Duplas ou Círculo; detalhe com os 4 passos do Círculo (boas-vindas, objectivos, actividades, encerrar) ou a estrutura das sessões das Duplas; marcar data.
- Guia da escola com as tarefas do manual (visitar a 6ª classe, recolher 10 inscrições por Círculo, encontros de 15 em 15 dias…).
- Recursos com as ferramentas do manual e o número da página.

## Problemas encontrados na app original (para o developer)

- Lâmpadas mal contadas: com 2 etapas concluídas devem estar 3 acesas (1 inicial + 1 por etapa); a app mostra 2.
- Mentor repetido: Ruth Patricio aparece na Dupla Star e «Sem dupla».
- Guia diz 4 duplas e 8 mentores; a escola tem 6 duplas e 21 mentores.
- Dupla Coral com 12 Mentorandos; o manual prevê 10.
- Zoom desactivado (`user-scalable=no`).
- A app não abre no computador nem no navegador sem instalar.
- Página Recursos vazia.

## Pedidos que ficaram em aberto

- Mudar também «Atenção especial» para «Situações de risco» no ecrã dos casos e na caixa do Início (por confirmar).
- Usar a média de todas as sessões também na caixa de Assiduidade do Início (hoje: últimos 5 Círculos).
- Mostrar «De onde é deslocado/a?» só para «Deslocado/a forçado/a» (hoje aparece nas duas opções).

## Alterações posteriores (Vercel via GitHub)

- Publicação: repositório `SHELCIACC/somos-luz-demo` (ramo `main`) → o Vercel publica sozinho a cada push.
- Ícone da app (lâmpada do manual sobre o verde), `manifest.webmanifest`, nome «Somos Luz» no ecrã principal.
- Layout adaptado a telemóveis pequenos (≤360 px) e tablets (≥600 px); sem ajustes para computador.
- Sessões: Super-Quatro (desenhos do manual) por cima da sessão em curso.
- «Percurso das sessões» só em Sessões (saiu do Início): sem lâmpadas, 4 símbolos das etapas (lâmpada, árvore, grupo, escola) — na cor da etapa quando concluída, preto em curso, cinzento por começar.
- Nova aba **Casos** (Gestão de casos), com base no documento «Gestão de Casos»: 1 Sinais de alerta (9 sinais + nota), 2 Registar caso (tipos de caso, pessoa da lista, idade, turno, já reportou?, Professor de Género em 24 h, prioridade Normal/Urgente/Crítico), 3 Dados dos casos (reportados, estado abertos/resolvidos, críticos e urgentes, lista com estado e prioridade).
- O reporte no registo de presenças usa agora os 9 sinais de alerta; os casos mostram tipo e prioridade.
- Menu de baixo com 6 abas; em ecrãs estreitos «Participantes» aparece como «Pessoas».
