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









