# 📄 Documento Oficial — Leadia V0

Versão: 0.1  
Status: Fonte única da verdade (Produto + Engenharia)  
Uso: Interno  

---

## 1. Visão do Produto

### 1.1 O que é o Leadia

O Leadia é uma secretária virtual 24/7 via WhatsApp, focada em transformar leads em pacientes, garantindo conversão em agendamentos de consulta para médicos individuais.

O produto automatiza o atendimento inicial, respostas administrativas e o processo de agendamento, mantendo comunicação humanizada e alinhada ao estilo do médico.

### 1.2 Cliente Primário (ICP)

- Cliente: Médico individual  
- Usuários do sistema:
  - Médico
  - Secretária / administrativo  

### 1.3 Problema que resolvemos

Médicos perdem consultas e receita porque:
- Leads não são respondidos rapidamente
- Atendimento administrativo consome tempo
- Falta consistência no processo de agendamento

O Leadia garante resposta imediata, organização e conversão.

### 1.4 Objetivo da Versão 0 (V0)

- Converter leads em agendamentos confirmados
- Operar como produto já vendável
- Validar aceitação do mercado, fluxo e operação

Métrica principal de sucesso: Conversão em agendamento

---

## 2. Definições Importantes

### 2.1 Lead vs Paciente

- Lead: Pessoa que inicia contato via WhatsApp sem consulta confirmada  
- Paciente: Lead que já possui consulta agendada ou histórico

Todo contato inicia como Lead.

---

## 3. Fluxo Geral do Usuário (WhatsApp)

- Canal único: WhatsApp
- O lead inicia a conversa
- Resposta automática desde a primeira mensagem
- Atendimento 100% automatizado na V0

---

## 4. Escopo da Versão 0

Inclui:
- Atendimento administrativo automatizado
- Agendamento inteligente com Google Agenda
- Gestão financeira apenas informativa

Fora da V0:
- Omnichannel
- IA autônoma
- Multi-clínicas

---

## 5. Inteligência Artificial na V0

Uso exclusivo para geração de texto.
IA não decide fluxo nem executa ações.

---

## 6. Arquitetura Geral

WhatsApp (WAHA) → Backend/Webhooks → n8n → Banco de Dados → Google Agenda

---

## 7. Stack Tecnológica

Frontend:
- Next.js, React, TypeScript, Tailwind, Vercel

Backend:
- Serverless-first
- APIs leves e webhooks

Orquestração:
- n8n (com uso consciente)

---

## 8. Modelo de Dados

- Lead
- Paciente
- User
- Agenda
- Conversa

---

## 9. LGPD & Segurança

- LGPD obrigatória desde o dia 1
- Armazenamento de dados sensíveis
- Consentimento e controle de acesso

---

## 10. Operação

- Operado pelo cliente
- Cliente altera apenas mensagens e configurações
- Mudanças estruturais exigem deploy

---

## 11. Evolução

V0 focada apenas em validação de produto e venda.

---

Documento interno. Toda mudança relevante deve atualizar este arquivo.
