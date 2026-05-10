# Notebooklm

https://notebooklm.google.com/notebook/2bbca27e-9d74-4403-8e60-fe94467759ab

## Objetivo

Nesse notebook, utilizei informações obtidas por meio de links e vídeos da instituição Estratégia Concursos, com foco em computação forense, além dos meus estudos na área de cibersegurança. Também apliquei os métodos de ensino do Professor Renato da Costa como base para auxiliar e orientar o aprendizado nessa área da Tecnologia da Informação.

## Fontes e links

### Documentos
https://www.estrategiaconcursos.com.br/curso/download/?aula=2138119
https://www.estrategiaconcursos.com.br/curso/download/?aula=3332478
https://www.estrategiaconcursos.com.br/curso/download/?aula=2138089

### Videos

https://www.youtube.com/live/sm4ssxyHgEY?si=CV-NCvnlIqTEel0L
https://www.youtube.com/live/anlGdJskrUM?si=SqTg14d4eH4U3hFQ
https://www.youtube.com/live/_qmUVgl0KXI?si=pGIATSJuWyJ2y-2Y

## Prompts para utilizar 

# 1- Se eu fosse um analista júnior de cibersegurança e precisasse investigar um computador suspeito pela primeira vez, quais seriam os passos básicos que eu deveria seguir para não cometer erros e conseguir identificar atividades suspeitas?

### Resposta

Como um analista júnior de cibersegurança iniciando sua primeira investigação em um computador suspeito, você deve seguir um protocolo rigoroso para garantir que as evidências sejam válidas e que a análise seja segura. Com base nas fontes, aqui estão os passos fundamentais e os sinais que você deve procurar:

### 1. Priorize a Coleta e a Volatilidade
A regra de ouro é que os dados digitais podem "sumir" ou ser alterados rapidamente.
*   **Capture dados voláteis primeiro:** Antes de desligar a máquina ou copiar arquivos, monitore o que está acontecendo na **memória RAM**, pois ataques modernos podem ser executados sem deixar rastros persistentes no disco rígido.
*   **Preserve o estado original:** Ao coletar imagens ou vídeos da cena e dos dispositivos, utilize formatos de arquivo brutos (**RAW**), que não sofrem tratamentos e garantem que a prova seja irrefutável.
*   **Use Atas Notariais:** Se precisar documentar conteúdos em redes sociais ou mensagens antes que sejam deletados, utilize este recurso para garantir validade jurídica.

### 2. Garanta a Integridade com Funções Hash
Para que sua investigação não seja invalidada por alegações de adulteração, você deve usar a "impressão digital" digital.
*   **Gere o Hash imediatamente:** Assim que coletar uma evidência, aplique uma **função Hash** (como MD5 ou SHA). O Hash garante a **integridade**, provando que o dado não foi modificado, inserido ou deletado desde a sua coleta.
*   **Cadeia de Custódia:** Mantenha registros detalhados (logs) de quem acessou a evidência e quando.

### 3. Monitore Atividades de Rede e Processos
Identificar o que o computador está "falando" e "fazendo" é crucial para detectar invasores.
*   **Detecte Sniffers:** Utilize ferramentas como **Wireshark** ou **tcpdump** para interceptar o tráfego. Um sinal de alerta é uma interface de rede operando em **modo promíscuo**, o que significa que o computador está capturando pacotes não destinados a ele (técnica de **MAC detection** pode ser usada para confirmar isso).
*   **Verifique conexões suspeitas:** Procure por **backdoors**, softwares que abrem "portas" de conexão para que criminosos tenham controle remoto da máquina.

### 4. Exemplos Práticos de Sinais de Alerta
Ao realizar a perícia, foque nestes itens comuns:
*   **Arquivo Hosts alterado:** Verifique o caminho `C:\Windows\System32\drivers\etc\hosts`. Se houver redirecionamentos estranhos para endereços IP desconhecidos, a máquina é vítima de **pharming**.
*   **Uso excessivo de recursos:** Se o computador apresentar lentidão súbita, alto consumo de CPU ou memória sem causa aparente, pode haver um **worm** se replicando ou um malware executando tarefas em segundo plano.
*   **Processos Ocultos:** Um **rootkit** pode estar sendo usado para esconder arquivos, diretórios e conexões de rede ativos.

### 5. Utilize Ambientes Seguros (Sandbox)
**Nunca execute um arquivo ou software suspeito diretamente no sistema principal.**
*   Utilize uma **sandbox**, que é uma área virtualizada isolada que emula uma máquina real. Nela, você pode observar o comportamento do malware sem colocar em risco a integridade do sistema operacional base ou da rede.

### Erros que Você Deve Evitar
1.  **Ignorar atualizações:** Investigar um sistema que não possui os últimos **patches de segurança** significa lidar com vulnerabilidades conhecidas que facilitam a vida do atacante.
2.  **Não usar logs:** Deixar de analisar os **logs de eventos** impede que você saiba exatamente o que foi acessado, por quem e quando.
3.  **Confiar apenas em antivírus:** Embora úteis, antivírus baseados em assinaturas podem não detectar ataques de **dia zero (zero-day)**, exigindo análise de comportamento e heurística.
4.  **Extremos na Tecnologia:** Lembre-se que em TI "não existem extremos"; desconfie de regras que pareçam rígidas demais ou imutáveis.

Seguindo esses passos, você transforma **dados** brutos em **informação** contextualizada, gerando o **conhecimento** necessário para um relatório final robusto.

# 2-  explique como um profissional de computação forense ou cibersegurança elabora um relatório de ataque cibernético ou incidente digital. Mostre quais informações são analisadas, como as evidências são organizadas, quais etapas devem existir no relatório, como os logs e provas são documentados e apresente um exemplo simples de relatório feito por um analista iniciante.

### Resposta

A elaboração de um relatório de ataque cibernético ou incidente digital é um processo técnico e documental que transforma **dados brutos** em **conhecimento** acionável para decisões judiciais ou corporativas. Com base nos materiais, um profissional de cibersegurança ou computação forense segue um rito sistemático para garantir a validade das provas.

Abaixo, detalho como esse relatório é estruturado e executado:

### 1. Informações e Dados Analisados
O investigador analisa diferentes camadas de dados para comprovar a **materialidade** (se o crime ocorreu) e a **autoria** (quem cometeu). As principais fontes são:
*   **Logs de Eventos:** Registros de sistemas e aplicativos que detalham **quem acessou, o que foi acessado e quando**.
*   **Tráfego de Rede:** Captura de pacotes (via ferramentas como **Wireshark** ou **tcpdump**) para identificar senhas em "claro" ou comunicações com servidores maliciosos.
*   **Memória RAM e Processos:** Análise de atividades voláteis para detectar ataques modernos que não deixam rastros no disco rígido (como *malwares* em memória).
*   **Metadados:** Informações sobre os arquivos, como autor, data de criação e formato (ex: padrão Dublin Core).

### 2. Organização e Preservação das Evidências
A organização deve seguir o princípio da **integridade**, garantindo que a prova não foi alterada.
*   **Cadeia de Custódia e Hashes:** É indispensável o uso de **funções Hash** (resumos digitais). O Hash funciona como uma "impressão digital": qualquer alteração no arquivo altera o Hash, invalidando a prova.
*   **Formatos Brutos (RAW):** Peritos utilizam formatos de imagem e vídeo sem tratamento (RAW) para que a evidência seja irrefutável.
*   **Atas Notariais:** Utilizadas para documentar conteúdos voláteis (como mensagens e redes sociais) antes que o criminoso os apague.

### 3. Etapas Obrigatórias do Relatório
O relatório deve seguir um fluxo lógico similar ao ciclo de vida da informação:
1.  **Sumário Executivo:** Visão geral do incidente (o que aconteceu e o impacto).
2.  **Escopo e Planejamento:** Definição dos limites da investigação e metas estabelecidas.
3.  **Metodologia e Coleta:** Descrição das ferramentas usadas e como os dados foram extraídos de forma segura.
4.  **Análise Técnica:** Fase de "transformação", onde os dados são limpos, filtrados e correlacionados para gerar insights.
5.  **Conclusão (Conhecimento):** Avaliação final sobre a confiabilidade e importância das provas, subsidiando a decisão do gestor ou do juiz.

### 4. Documentação de Logs e Provas
*   **Validação de Entradas e Erros:** Documentar como a aplicação reagiu a dados inesperados e se houve vazamento de informações em mensagens de erro.
*   **Auditoria:** Incluir trilhas de auditoria que mostrem a "irretratabilidade" (não repúdio), provando que o emissor não pode negar o envio da mensagem.
*   **Capturas de Tela:** Imagens de telas de monitoramento ou do código malicioso sendo executado.

### 5. Exemplo Simples de Relatório (Analista Iniciante)

> **RELATÓRIO DE INCIDENTE DIGITAL - 001/2026**
>
> **1. Resumo:** Identificada infecção por *Ransomware* em uma estação de trabalho no setor financeiro.
>
> **2. Evidências Coletadas:**
> *   **Arquivo:** `fatura_fake.exe` (encontrado na pasta de downloads).
> *   **Hash (SHA-256):** `a3b2c1...` (gerado imediatamente após a coleta).
> *   **Log de Rede:** Registro do Wireshark mostrando conexão externa para o IP `192.168.x.x` via protocolo FTP não criptografado.
>
> **3. Análise:** O usuário clicou em um link de *Phishing*. O malware foi carregado na memória RAM, criptografando arquivos locais e solicitando resgate em Bitcoin.
>
> **4. Conclusão:** O incidente violou a **disponibilidade** (arquivos inacessíveis) e a **integridade** (arquivos modificados pelo vírus).
>
> **5. Recomendações:** Aplicação de *patches* de segurança, atualização de antivírus e treinamento contra engenharia social.

Este processo garante que o relatório deixe de ser apenas um "amontoado de dados" para se tornar uma peça de **conhecimento e inteligência** estratégica.

# Miniguia de Estudo — Computação Forense e Cibersegurança

# 1. Resumo Estruturado do Assunto

## O que é Computação Forense?

A computação forense é a área da Tecnologia da Informação responsável por identificar, coletar, preservar, analisar e documentar evidências digitais relacionadas a incidentes cibernéticos, invasões, fraudes ou crimes digitais.

Seu principal objetivo é:

* descobrir o que aconteceu;
* identificar possíveis responsáveis;
* preservar provas digitais;
* gerar relatórios técnicos confiáveis.

## Relação entre Computação Forense e Cibersegurança

A cibersegurança atua na:

* proteção de sistemas,
* prevenção de ataques,
* monitoramento de ameaças.

Já a computação forense atua:

* após incidentes,
* durante investigações,
* na análise de evidências digitais.

As duas áreas trabalham juntas para:

* detectar ataques;
* entender como ocorreram;
* evitar novos incidentes.

# Processo Básico de Investigação Forense

## 1. Coleta de Evidências

O analista coleta:

* logs;
* arquivos;
* memória RAM;
* conexões de rede;
* dispositivos.

Objetivo:
preservar os dados originais sem alterações.

## 2. Preservação da Integridade

Durante a coleta são utilizados:

* funções Hash;
* cadeia de custódia;
* cópias forenses.

Isso garante que a prova não foi modificada.

## 3. Análise

Nesta etapa o profissional:

* identifica atividades suspeitas;
* analisa malware;
* verifica conexões externas;
* correlaciona eventos;
* cria timeline do ataque.

## 4. Documentação

O analista cria:

* relatórios técnicos;
* evidências organizadas;
* descrição dos incidentes;
* recomendações de segurança.

# Conceitos Importantes

## Volatilidade

Dados que podem desaparecer rapidamente:

* RAM;
* processos ativos;
* conexões abertas.

Por isso:
a memória RAM deve ser analisada primeiro.

## Hash

Código único que funciona como:

> impressão digital do arquivo.

Se o arquivo mudar:

* o Hash muda também.

## Sandbox

Ambiente isolado usado para:

* executar malware;
* analisar comportamento suspeito;
* evitar contaminação do sistema principal.

## Logs

Registros de atividades do sistema:

* login;
* erros;
* conexões;
* execução de programas.

São fundamentais para investigações.

# Principais Ferramentas

| Ferramenta | Função                  |
| ---------- | ----------------------- |
| Wireshark  | Análise de rede         |
| tcpdump    | Captura de pacotes      |
| Autopsy    | Computação forense      |
| FTK Imager | Imagem forense          |
| Volatility | Análise de memória RAM  |
| Wazuh      | Monitoramento e SIEM    |
| VirtualBox | Sandbox e virtualização |

# Principais Ameaças

| Ameaça     | Descrição                          |
| ---------- | ---------------------------------- |
| Malware    | Software malicioso                 |
| Ransomware | Criptografa arquivos               |
| Rootkit    | Esconde processos e arquivos       |
| Worm       | Se replica automaticamente         |
| Backdoor   | Permite acesso remoto oculto       |
| Phishing   | Roubo de informações               |
| Pharming   | Redirecionamento para sites falsos |

# Estrutura Básica de um Relatório Forense

## 1. Resumo do Incidente

Descrição geral do ocorrido.

## 2. Evidências Coletadas

* arquivos;
* logs;
* hashes;
* conexões.

## 3. Análise Técnica

Explicação do ataque e comportamento identificado.

## 4. Conclusão

Impactos e resultados da investigação.

## 5. Recomendações

Melhorias de segurança e prevenção.

# 2. Glossário de Conceitos

| Conceito           | Significado                            |
| ------------------ | -------------------------------------- |
| Computação Forense | Investigação de evidências digitais    |
| Cibersegurança     | Proteção de sistemas e redes           |
| Hash               | Identificador único de arquivo         |
| Cadeia de Custódia | Controle das evidências                |
| Malware            | Programa malicioso                     |
| Rootkit            | Malware que se esconde no sistema      |
| Ransomware         | Malware que sequestra arquivos         |
| Sandbox            | Ambiente isolado de testes             |
| SIEM               | Plataforma de monitoramento de eventos |
| Log                | Registro de atividade                  |
| RAM                | Memória volátil do computador          |
| IOC                | Indicadores de comprometimento         |
| Timeline           | Linha do tempo do ataque               |
| Backdoor           | Acesso oculto ao sistema               |
| Sniffer            | Ferramenta de captura de rede          |
| Phishing           | Golpe para roubo de dados              |
| Pharming           | Redirecionamento para site falso       |
| Zero-Day           | Vulnerabilidade desconhecida           |
| Patch              | Atualização de segurança               |

# 3. Prompts Reutilizáveis para Estudos Futuros

## Prompt 1 — Investigação Forense

> “Explique como um analista de computação forense investigaria um computador suspeito passo a passo, mostrando ferramentas utilizadas, coleta de evidências, análise de logs e criação do relatório final.”

## Prompt 2 — Relatório de Incidente

> “Crie um exemplo realista de relatório de incidente cibernético feito por um analista júnior, incluindo análise técnica, evidências, hashes, timeline e recomendações.”

## Prompt 3 — Estudo de Malware

> “Explique de forma simples como funciona um ransomware, quais sinais ele deixa no sistema e como um analista pode identificar esse tipo de ataque.”

## Prompt 4 — Análise de Rede

> “Ensine como utilizar o Wireshark para identificar conexões suspeitas em uma rede, mostrando exemplos simples de análise de tráfego.”

## Prompt 5 — Aprendizado para Iniciantes

> “Monte um roteiro de estudos para iniciantes em computação forense e cibersegurança, incluindo conceitos básicos, ferramentas e práticas recomendadas.”

## Prompt 6 — Simulação de Ataque

> “Crie um cenário fictício de ataque cibernético em uma empresa e explique como um profissional de segurança investigaria o incidente.”

## Prompt 7 — Explicação de Logs

> “Explique como analisar logs do Windows e Linux para identificar atividades suspeitas em um computador comprometido.”
