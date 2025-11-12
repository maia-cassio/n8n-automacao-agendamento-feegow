
<img width="1488" height="620" alt="feegow" src="https://github.com/user-attachments/assets/b453dad6-295a-42d5-832d-17b771cbc7bd" />

# n8n-automacao-agendamento-feegow

Automação de Agendamento de Clínicas (N8N + Feegow + Sonax)

Este projeto implementa um sistema completo de agendamento e gerenciamento de pacientes, orquestrado 100% via WhatsApp (utilizando a plataforma Sonax e a API Oficial) e executado por fluxos de automação N8N integrados à API da Feegow.

O sistema é capaz de guiar o paciente pela jornada completa, desde a verificação de cadastro até o agendamento final, consultando disponibilidade em tempo real.

##  Funcionalidades Principais

Este repositório contém 7 fluxos modulares do N8N:

### Fluxos de Utilidade (Gerenciamento de Pacientes)
* **[Fluxo 0] Verificar Paciente:** Recebe um CPF e verifica se o paciente já existe na base Feegow.
* **[Fluxo 1] Criar Paciente:** Recebe os dados de um novo paciente (Nome, CPF, Data Nasc., etc.) e o cadastra automaticamente na Feegow.
* **[Fluxo 2] Buscar Unidades:** Retorna uma lista formatada de todas as unidades/clínicas disponíveis.

### Fluxos de Agendamento (Jornada do Paciente)
* **[Fase 1] Buscar Especialidades:** Filtra especialidades por convênio ou particular.
* **[Fase 2] Buscar Profissionais:** Filtra profissionais com base na especialidade escolhida.
* **[Fase 3] Buscar Horários:** Busca e retorna a agenda (próximos 7 dias) do profissional escolhido.
* **[Fase 4] Agendar Consulta:** Recebe os dados finais (paciente, data, hora) e cria o agendamento na Feegow.

### Fluxos de Cancelamento
* **[Fase 6] Buscar Agendamentos:** Busca todos os agendamentos futuros de um paciente (baseado no CPF).

##  Stack de Tecnologias

* **Orquestração:** N8N
* **API de Gestão (EHR):** Feegow (API Oficial)
* **Plataforma de Conversa:** Sonax (API Oficial do WhatsApp)
* **Memória de Contexto:** Google Sheets (para persistir IDs entre as fases da conversa)
* **Testes:** Postman

*Projeto desenvolvido por Cassio Maia, Especialista em IA.*
