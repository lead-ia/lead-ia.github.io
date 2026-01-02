# 📄 Documento Oficial — LeadIA V0

**Versão:** 0.1  
**Status:** Fonte única da verdade (Produto + Engenharia)  
**Uso:** Interno  

---

## 1. Visão do Produto

### 1.1 O que é o Leadia

O **Leadia** é uma **secretária virtual 24/7 via WhatsApp**, focada em **transformar leads em pacientes**, garantindo **conversão em agendamentos de consulta** para médicos individuais.

O produto automatiza o atendimento inicial, respostas administrativas e o processo de agendamento, mantendo comunicação humanizada e alinhada ao estilo do médico.

---

### 1.2 Cliente Primário (ICP)

- **Cliente:** Médico individual  
- **Usuários do sistema:**
  - Médico
  - Secretária / administrativo  

---

### 1.3 Problema que resolvemos

Médicos perdem consultas e receita porque:
- Leads não são respondidos rapidamente
- Atendimento administrativo consome tempo
- Falta consistência no processo de agendamento

O Leadia garante **resposta imediata, organização e conversão**.

---

### 1.4 Objetivo da Versão 0 (V0)

- Converter leads em agendamentos confirmados
- Operar como **produto já vendável**
- Validar aceitação do mercado, fluxo e operação

**Métrica principal de sucesso:**  
➡️ **Conversão em agendamento**

---

## 2. Definições Importantes

### 2.1 Lead vs Paciente

- **Lead:** Pessoa que inicia contato via WhatsApp sem consulta confirmada  
- **Paciente:** Lead que já possui pelo menos uma consulta realizada

> Todo contato inicia como **Lead**.

---

## 3. Fluxo Geral do Usuário (WhatsApp)

### 3.1 Canal Único

- Todo o contato começa pelo **WhatsApp**
- Não existe omnichannel na V0

---

### 3.2 Início da Conversa

- O **Lead inicia o contato**
- O bot responde automaticamente desde a primeira mensagem

---

### 3.3 Atendimento Automatizado

O Leadia:
- Responde em até **2 minutos**
- Coleta:
  - Nome
  - CPF
  - Email
  - Telefone
- Envia:
  - Preço da consulta
  - Formas de pagamento (informativo)
  - Instruções pré-consulta

---

### 3.4 Agendamento

- Criação de **evento no Google Agenda do médico**
- Envio de **confirmação automática** ao lead/paciente
- Lembrete de confirmação **24h antes** (*configurável*)

---

### 3.5 Intervenção Humana e Alertas

- A V0 **não possui handoff humano como funcionalidade de produto**
- O Leadia opera com fluxos **automatizados do ponto de vista da conversa**
- Em situações específicas, o sistema **detecta mensagens que exigem atenção humana**
- Nesses casos, um **alerta é disparado ao médico/usuário**
- O alerta é enviado para um **segundo número de WhatsApp do médico**
- A resposta humana, quando ocorre, é **externa ao Leadia**, via WhatsApp direto
- O Leadia **não transfere, pausa ou gerencia** o controle da conversa na V0


## 4. Escopo da Versão 0

### 4.1 Funcionalidades Incluídas

#### 1. Atendimento administrativo automatizado
- Coleta de dados
- Respostas rápidas
- Envio de instruções (*configurável*)
- Orientações pré-consulta (*configurável*)
- Follow-ups automáticos:
  - Leads
  - Pacientes
  - Datas comemorativas
  - Aniversário
- Estilos de comunicação:
  - Acolhedor
  - Objetivo
  - Profissional
- Frases humanizadas adaptadas ao médico

---

#### 2. Agendamento inteligente
- Integração com Google Agenda
- Consultas online e presenciais
- Confirmação automática
- Lembretes configuráveis

---

#### 3. Gestão financeira (informativa)
- Envio de informações de pagamento
- Solicitação de comprovante

> ⚠️ O Leadia **não processa pagamentos**.  
> O dinheiro **não passa pela plataforma**.  
> O modelo de negócio é **mensalidade**.

---

### 4.2 Fora da Versão 0 (Explicitamente)

- Omnichannel
- Portabilização de clínicas
- Entendimento de áudio
- Autonomia avançada de IA
- Painel financeiro
- Multi-clínicas
- IA que decide fluxo

---

### 4.3 Complexidade de Conversa

- Fluxos **fechados**
- Caminhos pré-definidos
- IA não altera decisões

---

## 5. Inteligência Artificial na V0

### 5.1 Papel da IA

- Uso exclusivo para **geração de texto**
- Humanização das mensagens
- Adaptação ao estilo do médico

### 5.2 O que a IA NÃO faz

- Não decide fluxo
- Não altera regras
- Não classifica intenção
- Não executa ações

> IA é **cosmética**, não estrutural.

---

## 6. Arquitetura Geral

### 6.1 Visão de Alto Nível

WhatsApp (WAHA)
↓
Backend / Webhooks
↓
n8n (Regras de negócio)
↓
Banco de Dados
↓
Google Agenda / Serviços externos


---

## 7. Stack Tecnológica (V0)

### 7.1 Frontend
- Next.js
- React
- TypeScript
- Tailwind CSS
- Vercel

Uso:
- Landing page
- Painel simples
- Configurações básicas

---

### 7.2 Backend
- Serverless-first
- APIs leves
- Webhooks

**Decisão em aberto:**
- AWS Lambda vs Vercel Functions  
- CI/CD via GitHub para garantir controle dos endpoints

---

### 7.3 Orquestração (Core da V0)

- **n8n**
- Centraliza:
  - Regras de negócio
  - Fluxos
  - Integrações

**Ressalvas:**
- Inflexibilidade percebida pelo time
- Uso consciente
- Evitar lógica excessivamente complexa
- Planejar saída futura

---

### 7.4 WhatsApp
- WAHA (WhatsApp HTTP API)

---

### 7.5 Persistência de Dados
- Banco de dados desde o início
- Sheets **não são** fonte da verdade

---

## 8. Modelo de Dados (Entidades)

- Lead
- Paciente
- User
- Agenda
- Conversa

---

## 9. LGPD & Segurança

- LGPD **obrigatória desde o dia 1**
- Dados sensíveis (CPF) armazenados
- Requisitos mínimos:
  - Consentimento
  - Controle de acesso
  - Variáveis de ambiente
  - Webhooks protegidos

---

## 10. Operação da V0

### 10.1 Quem opera
- Cliente (médico)

### 10.2 O que o cliente pode alterar
- Mensagens
- Configurações
- Estilo de comunicação

❌ Não altera fluxos  
❌ Não altera lógica  

---

### 10.3 Deploy & Mudanças
- Mudanças estruturais exigem deploy
- Configurações não exigem deploy

---

## 11. Escalabilidade & Evolução

### 11.1 Foco da V0
- Validar produto
- Validar fluxo
- Validar venda

### 11.2 Fora do escopo
- Escala enterprise
- Multi-clínicas
- Alta complexidade operacional

---

## 12. Considerações Finais

Este documento define:
- O que é o Leadia V0
- O que ele faz
- O que ele não faz
- Como é construído
- Quem decide o quê

Toda mudança relevante deve atualizar este documento.
