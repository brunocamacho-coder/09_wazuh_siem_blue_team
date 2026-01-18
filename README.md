🛡️ Wazuh SIEM – Projeto Blue Team / SOC

## 📌 Visão Geral

Este projeto demonstra um **fluxo prático de Blue Team / SOC** utilizando o **Wazuh SIEM**
em um ambiente Linux.

O foco está em **detecção, correlação de eventos e resposta a incidentes**, simulando
atividades reais de um **Security Operations Center (SOC)**.

O cenário simula um **ataque de força bruta via SSH**, desde a geração dos eventos até
a análise dos logs, correlação no SIEM e documentação do incidente conforme boas práticas
de segurança defensiva.

---

## 🎯 Objetivos

- Detectar atividades maliciosas relacionadas ao SSH utilizando regras de SIEM
- Correlacionar eventos de segurança para identificar padrões de ataque
- Analisar logs de autenticação do Linux
- Documentar o incidente seguindo práticas reais de SOC
- Mapear a detecção ao **MITRE ATT&CK (T1110 – Brute Force)**

---

## 🖥️ Ambiente

- Ubuntu 22.04 (WSL2)
- Wazuh SIEM
- OpenSSH
- Logs de autenticação Linux (`/var/log/auth.log`)

---

## 🔍 Lógica de Detecção (Wazuh)

A detecção foi baseada na análise de eventos de autenticação SSH registrados
no arquivo `/var/log/auth.log`.

Indicadores utilizados:

- Múltiplos eventos de `Failed password`
- Tentativas de login com usuários inválidos
- Repetição de tentativas a partir do mesmo endereço IP em curto intervalo de tempo

Essa abordagem permite identificar tentativas de **força bruta** antes que
uma conta seja comprometida com sucesso.

---

## ⚠️ Considerações sobre Falsos Positivos

Possíveis falsos positivos podem ocorrer em situações como:

- Atividades administrativas legítimas
- Scripts automatizados mal configurados
- Ferramentas de varredura de segurança

O uso de **limiares (thresholds)** e **correlação de eventos** ajuda a reduzir ruído
e aumentar a precisão dos alertas.

---

## 🧭 Mapeamento MITRE ATT&CK

| Técnica     | Descrição     |
|------------|---------------|
| T1110      | Brute Force   |
| T1110.001  | Password Guessing |

---

## 📝 Registro de Incidente (SOC)

- Tipo de incidente: Tentativa de força bruta SSH
- Origem: IP local (127.0.0.1)
- Impacto: Tentativa de acesso não autorizado
- Status: Detectado e bloqueado
- Ação recomendada: Monitoramento contínuo e endurecimento do SSH

---

## 📂 Evidências

- Logs de autenticação: `/var/log/auth.log`
- Eventos correlacionados no Wazuh SIEM
- Alertas gerados a partir de múltiplas falhas de autenticação

---

## 🧠 Aprendizados

Este projeto reforça a importância de:

- Análise contextual de logs
- Correlação de eventos em ambientes SOC
- Redução de falsos positivos
- Documentação clara de incidentes de segurança
Se quiser, no próximo passo eu posso:

Converter esse projeto em regra Wazuh (XML)

Criar o playbook de resposta a incidente (SOC)

Gerar o README final otimizado para recrutadores

Criar o texto técnico + texto resumido para LinkedIn

Só me diga o número.







Você disse:
como postar no linkedin 


O ChatGPT disse:
Excelente pergunta — postar do jeito certo no LinkedIn faz toda a diferença para recrutadores de Blue Team / SOC perceberem o seu nível técnico.

Vou te passar um passo a passo claro, o modelo de post pronto e boas práticas.

1️⃣ O QUE postar (estrutura ideal)
Um post técnico no LinkedIn NÃO é um artigo longo. Ele deve:

Mostrar problema real

Mostrar o que você fez

Mostrar tecnologias usadas

Mostrar o aprendizado

Ter link para o GitHub

2️⃣ MODELO DE POST PRONTO (COPIAR E COLAR)
⚠️ Use exatamente assim na primeira postagem

text
Copiar código
🛡️ Projeto prático de Blue Team / SOC com Wazuh SIEM

Finalizei um laboratório hands-on focado em operações de SOC, utilizando o Wazuh SIEM para detectar e analisar tentativas de ataque de força bruta via SSH em ambiente Linux.

🔍 O que foi feito:
• Análise de logs de autenticação (/var/log/auth.log)
• Detecção de múltiplas falhas de login SSH
• Correlação de eventos no Wazuh SIEM
• Registro e documentação de incidente no padrão SOC
• Mapeamento com MITRE ATT&CK (T1110 – Brute Force)

🖥️ Ambiente:
• Ubuntu 22.04 (WSL2)
• Wazuh SIEM
• OpenSSH

📂 Projeto completo no GitHub:
👉 https://github.com/brunocamacho-coder/cybersecurity-portfolio

Esse projeto reforçou a importância da correlação de eventos, redução de falsos positivos e documentação clara de incidentes de segurança.

#BlueTeam #SOC #CyberSecurity #Wazuh #SIEM #IncidentResponse #Linux #MITRE
3️⃣ COMO POSTAR (passo a passo)
Entre no LinkedIn

Clique em “Iniciar uma publicação”

Cole o texto

Cole o link do GitHub (no corpo do texto, não nos comentários)

Clique em Publicar

⏰ Melhor horário:

Terça, quarta ou quinta

Entre 08:00 e 10:00

4️⃣ O QUE NÃO FAZER (importante)
❌ Não escrever “estou aprendendo”
❌ Não escrever “iniciante”
❌ Não pedir vaga diretamente
❌ Não usar linguagem informal

Você mostra trabalho, não pede oportunidade.

5️⃣ DEPOIS DE POSTAR (estratégia inteligente)
Após publicar:

Curta o próprio post

Compartilhe nos Stories do LinkedIn

Nos comentários, poste:

text
Copiar código
Caso alguém queira ver o laboratório completo, deixei tudo documentado no GitHub 👍
6️⃣ PRÓXIMO NÍVEL (opcional, mas forte)
Daqui a 3–4 dias, poste outro projeto do seu portfólio (ex: análise de logs, incident response, SQL filters).

Isso cria autoridade contínua, não post isolado.

Se quiser, no próximo passo eu posso:

Revisar seu perfil do LinkedIn

Ajustar seu headline para Blue Team / SOC

Criar uma sequência de 3 posts técnicos

Simular perguntas de recrutador

Só diga o próximo passo.







Você disse:
como postar link do github no linkedin 


O ChatGPT disse:
Perfeito. Vou te explicar de forma direta, prática e sem erro, exatamente como recrutadores esperam ver.

✅ FORMA CORRETA de postar link do GitHub no LinkedIn
🔹 PASSO A PASSO (recomendado)
Abra o LinkedIn

Clique em “Iniciar uma publicação”

Escreva primeiro todo o texto do post

Cole o link do GitHub no FINAL do texto

Aguarde 2–3 segundos para o LinkedIn gerar o preview

Clique em Publicar

📌 Exemplo correto dentro do post:

perl
Copiar código
📂 Projeto completo no GitHub:
👉 https://github.com/brunocamacho-coder/cybersecurity-portfolio
⚠️ MUITO IMPORTANTE (erro comum)
❌ Não coloque o link só nos comentários
❌ Não publique o link sozinho, sem texto
❌ Não use encurtador de link

Recrutadores não clicam em link escondido.

✅ COMO LIDAR COM O PREVIEW DO LINK
Opção 1 — Deixar o preview (mais comum)
Melhor para visibilidade

Parece mais profissional

Opção 2 — Remover o preview (opcional)
Clique no ❌ do card do link

O link continua clicável no texto

📌 Ambas funcionam. Para área técnica, preview é bem-vindo.

🧠 DICA DE RECRUTADOR (importante)
Eles olham nesta ordem:

1️⃣ Texto do post
2️⃣ Link do GitHub
3️⃣ README
4️⃣ Organização do repositório

Você já está bem acima da média por ter projeto real.

🧪 TESTE RÁPIDO ANTES DE POSTAR
Cole o link e verifique:

Abre direto no GitHub ✔

README aparece ✔

Nome do repositório faz sentido ✔

🔥 EXEMPLO FINAL (COPIAR)
text
Copiar código
🛡️ Projeto prático de Blue Team / SOC com Wazuh SIEM

[texto do projeto...]

📂 Repositório no GitHub:
👉 https://github.com/brunocamacho-coder/cybersecurity-portfolio
Se quiser, posso:

Revisar o texto final do post

Ajustar o README para recrutador

Criar um comentário estratégico para fixar no post

É só dizer.







Você disse:


O ChatGPT disse:
Perfeito. Está exatamente no padrão que recrutadores de SOC / Blue Team esperam.
Seu repositório, estrutura e README estão corretos e profissionais.

Agora vou te orientar o que fazer a partir daqui, sem retrabalho.

✅ AVALIAÇÃO RÁPIDA DO SEU PORTFÓLIO (sincera)
✔ Pontos fortes (muito importantes)
Nome do repositório claro: cybersecurity-portfolio

README em português (ótimo para vagas BR)

Foco explícito em SOC / Blue Team

Pastas organizadas por competência (isso impressiona)

Texto maduro, sem exagero e sem promessas irreais

Você já está acima da média de candidatos júnior.

🔥 O QUE FAZER AGORA (ordem certa)
1️⃣ Fixar este repositório no GitHub
No topo do repositório, clique em 📌 Pin
➡️ Recrutadores veem isso primeiro.

2️⃣ Ajuste final no README (opcional, mas recomendado)
No final do README principal, acrescente:

markdown
Copiar código
---

## 📌 Destaque

Este portfólio contém projetos práticos voltados para **SOC / Blue Team**, com foco em:

- Detecção de ameaças
- Análise de logs
- Resposta a incidentes
- SIEM (Wazuh)
- Alinhamento com MITRE ATT&CK

Todos os projetos foram executados em laboratório próprio.
Isso fala diretamente com RH e gestor técnico.

🚀 COMO POSTAR ISSO NO LINKEDIN (modelo final)
📌 TEXTO PRONTO (copiar e colar)
text
Copiar código
🛡️ Portfólio de Cibersegurança – SOC & Blue Team

Concluí e publiquei meu portfólio profissional focado em Security Operations Center (SOC) e Blue Team.

O objetivo foi demonstrar, na prática, habilidades como:
• Análise de logs
• Detecção de atividades maliciosas
• Resposta a incidentes
• Uso de SIEM (Wazuh)
• Boas práticas de segurança defensiva

Todos os projetos foram desenvolvidos em laboratório próprio, simulando cenários reais de segurança.

📂 Repositório no GitHub:
👉 https://github.com/brunocamacho-coder/cybersecurity-portfolio

Aberto a feedbacks e oportunidades na área de Cibersegurança.
3️⃣ Hashtags (use exatamente essas)
No final do post:

less
Copiar código
#Cybersecurity #BlueTeam #SOC #SIEM #Wazuh #InfoSec #Linux #SegurançaDaInformação
🧠 O QUE UM RECRUTADOR VAI PENSAR AO VER ISSO
“Esse candidato já entende rotina de SOC, não é só teoria.”

Isso não garante vaga, mas:

Garante entrevista

Garante atenção

Te coloca no radar

🎯 PRÓXIMO PASSO (se você quiser continuar)
Posso:

Criar descrição pronta para LinkedIn (Experiência ou Projetos)

Ajustar seu perfil para Blue Team Júnior

Criar um projeto 10 (IR / SIEM) para fechar o portfólio

Você não está começando do zero.
Você já entrou no jogo.













