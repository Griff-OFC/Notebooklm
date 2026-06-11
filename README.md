# 🛡️ Guia de Estudos: Computação Forense e Cibersegurança

![Status](https://img.shields.io/badge/Status-Em%20Construção-green)
![Tema](https://img.shields.io/badge/Tema-Cibersegurança-blue)
![Tema](https://img.shields.io/badge/Tema-Forense-darkblue)

> Este projeto consolida informações geradas com o auxílio do [NotebookLM](https://notebooklm.google.com/notebook/2bbca27e-9d74-4403-8e60-fe94467759ab), com foco em computação forense e cibersegurança.

---

## 📋 Índice

- [Objetivo](#-objetivo)
- [Fontes e Referências](#-fontes-e-referências)
- [Miniguia de Estudo](#-miniguia-de-estudo)
  - [O que é Computação Forense?](#o-que-é-computação-forense)
  - [Processo de Investigação](#processo-básico-de-investigação-forense)
  - [Conceitos Importantes](#conceitos-importantes)
  - [Principais Ferramentas](#principais-ferramentas)
  - [Principais Ameaças](#principais-ameaças)
  - [Glossário](#glossário-de-conceitos)
- [Q\&A: Casos Práticos](#-qa-casos-práticos)
- [Prompts para Estudos Futuros](#-prompts-para-estudos-futuros)

---

## 🎯 Objetivo

Neste repositório, utilizo informações obtidas por meio de links e vídeos da instituição **Estratégia Concursos** (com foco em computação forense), além dos meus estudos pessoais na área de cibersegurança. O material também aplica os métodos de ensino do **Professor Renato da Costa** como base para auxiliar e orientar o aprendizado na área de Tecnologia da Informação.

---

## 📚 Fontes e Referências

### 📄 Documentos (Estratégia Concursos)
- [Aula 2138119](https://www.estrategiaconcursos.com.br/curso/download/?aula=2138119)
- [Aula 3332478](https://www.estrategiaconcursos.com.br/curso/download/?aula=3332478)
- [Aula 2138089](https://www.estrategiaconcursos.com.br/curso/download/?aula=2138089)

### 🎥 Vídeos
- [Live 1 - Estratégia](https://www.youtube.com/live/sm4ssxyHgEY?si=CV-NCvnlIqTEel0L)
- [Live 2 - Estratégia](https://www.youtube.com/live/anlGdJskrUM?si=SqTg14d4eH4U3hFQ)
- [Live 3 - Estratégia](https://www.youtube.com/live/_qmUVgl0KXI?si=pGIATSJuWyJ2y-2Y)

---

## 📖 Miniguia de Estudo

### O que é Computação Forense?
A computação forense é a área da Tecnologia da Informação responsável por identificar, coletar, preservar, analisar e documentar evidências digitais relacionadas a incidentes cibernéticos, invasões, fraudes ou crimes digitais.

**Seu principal objetivo é:**
- Descobrir o que aconteceu;
- Identificar possíveis responsáveis;
- Preservar provas digitais;
- Gerar relatórios técnicos confiáveis.

**Relação entre Computação Forense e Cibersegurança:**
- **Cibersegurança atua na:** Proteção de sistemas, prevenção de ataques e monitoramento de ameaças.
- **Computação Forense atua:** Após incidentes, durante investigações e na análise de evidências digitais.

Ambas trabalham juntas para detectar ataques, entender como ocorreram e evitar novos incidentes.

### Processo Básico de Investigação Forense

1. **Coleta de Evidências:** O analista coleta logs, arquivos, memória RAM, conexões de rede e dispositivos. *Objetivo: preservar os dados originais sem alterações.*
2. **Preservação da Integridade:** Uso de funções Hash, cadeia de custódia e cópias forenses. Isso garante que a prova não foi modificada.
3. **Análise:** Identificação de atividades suspeitas, análise de malware, verificação de conexões externas e criação de *timeline* do ataque.
4. **Documentação:** Criação de relatórios técnicos com evidências organizadas, descrição dos incidentes e recomendações de segurança.

### Conceitos Importantes

- **Volatilidade:** Dados que podem desaparecer rapidamente (RAM, processos ativos, conexões abertas). A memória RAM deve ser analisada primeiro.
- **Hash:** Código único que funciona como uma "impressão digital" do arquivo. Se o arquivo mudar, o Hash também muda.
- **Sandbox:** Ambiente isolado usado para executar malware, analisar comportamento suspeito e evitar a contaminação do sistema principal.
- **Logs:** Registros de atividades do sistema (login, erros, conexões). São fundamentais para investigações.

### Principais Ferramentas

| Ferramenta | Função |
|---|---|
| **Wireshark** | Análise de rede |
| **tcpdump** | Captura de pacotes |
| **Autopsy** | Computação forense |
| **FTK Imager** | Imagem forense |
| **Volatility** | Análise de memória RAM |
| **Wazuh** | Monitoramento e SIEM |
| **VirtualBox** | Sandbox e virtualização |

### Principais Ameaças

| Ameaça | Descrição |
|---|---|
| **Malware** | Software malicioso |
| **Ransomware** | Criptografa arquivos e pede resgate |
| **Rootkit** | Esconde processos e arquivos no sistema |
| **Worm** | Se replica automaticamente pela rede |
| **Backdoor** | Permite acesso remoto oculto |
| **Phishing** | Engenharia social para roubo de informações |
| **Pharming** | Redirecionamento de tráfego para sites falsos |

### Glossário de Conceitos

| Conceito | Significado |
|---|---|
| **Cadeia de Custódia** | Controle cronológico e documentado das evidências |
| **SIEM** | Plataforma de monitoramento e correlação de eventos |
| **IOC** | Indicadores de Comprometimento (*Indicators of Compromise*) |
| **Timeline** | Linha do tempo do ataque |
| **Sniffer** | Ferramenta de interceptação/captura de tráfego de rede |
| **Zero-Day** | Vulnerabilidade desconhecida pelo fabricante |
| **Patch** | Atualização de correção de segurança |

---

## 🔍 Q&A: Casos Práticos

<details>
<summary><b>1. Como um analista júnior deve investigar um computador suspeito pela primeira vez?</b></summary>

<br>

Como um analista júnior iniciando sua primeira investigação, você deve seguir um protocolo rigoroso para garantir a validade das evidências:

1. **Priorize a Coleta e a Volatilidade:** Capture dados voláteis primeiro (memória RAM). Preserve o estado original utilizando arquivos brutos (RAW). Use Atas Notariais para conteúdos voláteis em redes sociais.
2. **Garanta a Integridade com Funções Hash:** Gere o Hash (MD5, SHA) imediatamente após a coleta para provar que a evidência não foi adulterada. Mantenha a Cadeia de Custódia.
3. **Monitore Atividades e Processos:** Use ferramentas como Wireshark. Procure por interfaces em modo promíscuo ou portas abertas (*backdoors*).
4. **Sinais de Alerta Comuns:** Alterações no arquivo `hosts` (sinal de pharming), uso excessivo de recursos (worms/mineradores) ou processos ocultos (rootkits).
5. **Utilize Ambientes Seguros (Sandbox):** Nunca execute arquivos suspeitos no sistema principal.

**Erros a Evitar:**
- Ignorar atualizações (patches).
- Não consultar logs de eventos.
- Confiar exclusivamente no antivírus.
- Ser extremo nas metodologias sem avaliar o contexto.
</details>

<details>
<summary><b>2. Como elaborar um relatório de ataque cibernético ou incidente digital?</b></summary>

<br>

O relatório transforma dados brutos em conhecimento acionável. Deve-se analisar logs, tráfego, memória RAM e metadados, sempre preservando a integridade (Hashes, RAW).

**Etapas Obrigatórias:**
1. **Sumário Executivo:** Visão geral e impacto.
2. **Escopo e Planejamento:** Limites da investigação.
3. **Metodologia e Coleta:** Ferramentas e procedimentos.
4. **Análise Técnica:** Correlação de dados e insights.
5. **Conclusão:** Avaliação final e recomendações.

**Exemplo de Relatório Simples:**
> **RELATÓRIO DE INCIDENTE DIGITAL - 001/2026**
> 
> **1. Resumo:** Infecção por *Ransomware* no setor financeiro.
> 
> **2. Evidências:** Arquivo `fatura_fake.exe`; Hash `a3b2c1...`; Log de rede conectando via FTP a `192.168.x.x`.
> 
> **3. Análise:** Phishing carregado na RAM, arquivos criptografados.
> 
> **4. Conclusão:** Violação de disponibilidade e integridade.
> 
> **5. Recomendações:** Patches, atualização de AV e treinamento.
</details>

---

## 🤖 Prompts para Estudos Futuros

Você pode utilizar estes prompts no ChatGPT, NotebookLM ou outras IAs para aprofundar seus conhecimentos:

1. **Investigação Forense:**
   > “Explique como um analista de computação forense investigaria um computador suspeito passo a passo, mostrando ferramentas utilizadas, coleta de evidências, análise de logs e criação do relatório final.”

2. **Relatório de Incidente:**
   > “Crie um exemplo realista de relatório de incidente cibernético feito por um analista júnior, incluindo análise técnica, evidências, hashes, timeline e recomendações.”

3. **Estudo de Malware:**
   > “Explique de forma simples como funciona um ransomware, quais sinais ele deixa no sistema e como um analista pode identificar esse tipo de ataque.”

4. **Análise de Rede:**
   > “Ensine como utilizar o Wireshark para identificar conexões suspeitas em uma rede, mostrando exemplos simples de análise de tráfego.”

5. **Aprendizado para Iniciantes:**
   > “Monte um roteiro de estudos para iniciantes em computação forense e cibersegurança, incluindo conceitos básicos, ferramentas e práticas recomendadas.”

6. **Simulação de Ataque:**
   > “Crie um cenário fictício de ataque cibernético em uma empresa e explique como um profissional de segurança investigaria o incidente.”

7. **Explicação de Logs:**
   > “Explique como analisar logs do Windows e Linux para identificar atividades suspeitas em um computador comprometido.”

---
*Documento otimizado para estudos de Cibersegurança e Forense.*
