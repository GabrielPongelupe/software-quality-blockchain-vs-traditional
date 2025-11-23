# Plano de Experimento – Scoping e Planejamento  
## **Comparação de Métricas de Qualidade entre Software Tradicional e Software Baseado em Blockchain: Um Estudo Empírico**

---

## 1. Identificação Básica

### 1.1 Título do Experimento  
**Comparação de Métricas de Qualidade entre Software Tradicional e Software Baseado em Blockchain: Um Estudo Empírico**

### 1.2 ID / Código  
**ES-BC-QUAL-2025-01**

### 1.3 Versão do Documento e Histórico de Revisão  
- **1.0 — 23/11/2025:** Versão inicial do plano de experimento, contendo escopo, objetivos, hipóteses, variáveis e metodologia proposta.  
*(Novas versões serão adicionadas conforme o andamento da coleta, análise e ajustes metodológicos.)*

### 1.4 Datas  
- **Data de criação:** 23 de novembro de 2025  
- **Última atualização:** 23 de novembro de 2025  
- **Período estimado de execução:** Novembro a Dezembro de 2025  
- **Responsável pelas atualizações:** Gabriel Pongelupe

### 1.5 Autores  
**Gabriel Pongelupe – Engenharia de Software**  
Responsável pela elaboração do documento, definição metodológica, execução da coleta e síntese dos resultados.  


### 1.6 Responsável Principal (PI – Principal Investigator)  
**Gabriel Pongelupe**, atuando como pesquisador principal deste estudo.  
Responsabilidades:  
- definição das questões de pesquisa;  
- elaboração das hipóteses e planejamento experimental;  
- seleção e preparação dos artefatos;  
- execução dos processos de coleta e normalização;  
- aplicação das técnicas estatísticas;  
- interpretação dos resultados e construção da conclusão final.

### 1.7 Projeto / Iniciativa Relacionada  
Este experimento integra as atividades da disciplina **Medição e Experimentação em Engenharia de Software**, cujo objetivo é aplicar rigor científico para investigar impactos de decisões de projeto e arquitetura em sistemas reais.  

O estudo se relaciona com temas contemporâneos como:  
- avaliação de qualidade em diferentes paradigmas de desenvolvimento;  
- impacto da descentralização, imutabilidade e custos de execução em métricas objetivas de software;  
- comparação empírica entre smart contracts e módulos tradicionais;  
- evolução das práticas de engenharia no ecossistema blockchain;  
- identificação de padrões arquiteturais decorrentes de restrições próprias de ambientes EVM e similares.

Trata-se de uma iniciativa voltada a compreender, com base em evidências, como o paradigma blockchain influencia atributos essenciais de qualidade que afetam manutenção, complexidade e custo de evolução.

---

## 2. Contexto e Problema

### 2.1 Descrição do Problema / Oportunidade  
A crescente adoção de tecnologias blockchain introduziu um novo paradigma de desenvolvimento de software, caracterizado por descentralização, execução determinística, imutabilidade do código implantado, e custos explícitos de processamento (gas) em ambientes como a Ethereum Virtual Machine (EVM). Embora esses fatores sejam fundamentais para garantir segurança e confiabilidade, eles impõem restrições arquiteturais e de design que podem alterar profundamente propriedades estruturais do software.

Enquanto sistemas tradicionais evoluem com maior flexibilidade – permitindo refatorações, atualizações incrementais e mudanças de arquitetura ao longo do tempo –, sistemas baseados em blockchain lidam com limitações práticas como:

- **Impossibilidade ou alto custo de atualizar smart contracts após o deploy**;  
- **Penalidade financeira associada à complexidade e ao tamanho do código (gas)**;  
- **Necessidade de minimizar superfícies de ataque**;  
- **Ambiente de execução altamente restrito, com limitações de estado, loops e armazenamento**.

Em consequência, surge uma oportunidade de pesquisa: **compreender, de maneira empírica e mensurável, como essas características afetam atributos clássicos de qualidade**, como complexidade, manutenibilidade, tamanho do código e modularidade.

Esse estudo busca preencher uma lacuna importante: embora existam trabalhos sobre verificação de segurança em smart contracts, **há pouca investigação empírica comparando diretamente métricas de software tradicionais com métricas de software blockchain**, o que é fundamental para entender o impacto real desse novo paradigma sobre o desenvolvimento e evolução de sistemas.

---

### 2.2 Relevância Técnica, Científica e Industrial  
A relevância deste experimento se manifesta em múltiplas esferas:

#### **Para engenheiros de software e desenvolvedores de smart contracts**  
O estudo pode orientar decisões práticas sobre design, modularização, complexidade desejável e estratégias de manutenção, especialmente em ambientes onde erros podem resultar em perdas financeiras irreversíveis.

#### **Para equipes de auditoria, segurança e qualidade**  
Auditores lidam diariamente com a necessidade de compreender estruturas de smart contracts e avaliar riscos; métricas comparativas podem oferecer indicadores objetivos para priorizar pontos críticos.

#### **Para a comunidade acadêmica**  
Blockchain representa um novo tipo de artefato de software, com restrições distintas das estudadas em modelos tradicionais. Entender como essas restrições influenciam métricas pode abrir novas linhas de pesquisa sobre qualidade, evolução, arquiteturas distribuídas e engenharia empírica.

#### **Para indústrias que dependem de contratos inteligentes**  
Setores como finanças descentralizadas (DeFi), rastreabilidade, logística, identidade digital e governança distribuída necessitam de maior previsibilidade, escalabilidade e segurança. Evidências sobre complexidade e manutenibilidade podem influenciar:

- custos de desenvolvimento;  
- esforço de manutenção;  
- riscos operacionais;  
- viabilidade de novos produtos baseados em blockchain.

---

### 2.3 Contexto Tecnológico e de Engenharia  
O experimento é conduzido com base em **projetos open-source** disponibilizados em plataformas como GitHub e GitLab, incluindo:

- smart contracts escritos em **Solidity** ou **Vyper**;  
- aplicações tradicionais em linguagens amplamente usadas (como TypeScript, Java, Python, Go).

Esses repositórios oferecem dados relevantes, como:

- histórico completo de commits;  
- racional de decisões arquiteturais em issues e pull requests;  
- auditorias, testes, padrões de design e práticas adotadas;  
- presença de ferramentas de análise estática e CI/CD.

Esse ambiente funciona como um **laboratório natural** para observar como diferentes paradigmas influenciam características objetivas de software, permitindo comparações quantitativas e qualitativas entre:

- sistemas descentralizados;  
- sistemas tradicionais monolíticos ou distribuídos;  
- diferentes estilos de modularidade;  
- diferentes impactos de restrições ambientais.

---

### 2.4 Trabalhos e Evidências Prévias  
Embora existam numerosos estudos sobre segurança em blockchain, a área de **métricas de qualidade aplicada a smart contracts** ainda é emergente. Alguns referenciais incluem:

- **Chen et al.** — análise de vulnerabilidades e padrões de desenvolvimento em smart contracts.  
- **Luu et al. (Oyente)** — identificação de padrões de execução e armadilhas relacionadas a complexidade.  
- **Kalra et al. (ZEUS)** — verificação formal e propriedades estruturais de contratos.  
- Estudos clássicos sobre métricas tradicionais:  
  - Chidamber & Kemerer (CK Metrics, 1994);  
  - Basili et al., complexidade e manutenibilidade;  
  - Pressman, Sommerville e a literatura base de Engenharia de Software.

Apesar desses trabalhos, **faltam estudos comparativos diretos entre sistemas blockchain e sistemas tradicionais utilizando as mesmas métricas de qualidade**, o que reforça a importância deste experimento.

---

### 2.5 Referencial Teórico e Empírico Essencial  
O experimento se fundamenta em uma combinação de literatura clássica e nova teoria emergente:

#### **Métricas de Engenharia de Software**
Baseia-se em modelos consagrados para medir complexidade, tamanho e manutenibilidade, como:

- Complexidade ciclomática (McCabe)
- Maintainability Index  
- LOC (Lines of Code)  
- Profundidade de aninhamento  
- Coesão e acoplamento (CK Metrics)

#### **Princípios de Design de Software**
Aplicados para contextualizar o impacto das restrições de blockchain:

- modularidade e encapsulamento;  
- minimização da complexidade;  
- princípio KISS (Keep It Simple, Stupid), amplamente adotado em smart contracts;  
- limitação de abstrações complexas devido ao custo de gas;  
- importância da previsibilidade e determinismo.

#### **Particularidades de Smart Contracts**
Incluem:

- execução em ambiente EVM;  
- custo por instrução computacional;  
- imutabilidade do código após o deploy;  
- padrões como “proxy pattern” para contornar limitações de atualização;  
- necessidade de minimizar superfícies de ataque e pontos de falha.

Esses elementos funcionam como lentes analíticas para interpretar resultados do experimento, permitindo discutir não apenas *o que* as métricas indicam, mas *por que* elas se comportam de forma distinta entre os dois paradigmas.

---
# 3. Objetivos e Questões (Goal / Question / Metric – GQM)

## 3.1 Objetivo geral (formulado no template GQM)
O objetivo geral deste estudo, seguindo o paradigma GQM, é **analisar diferenças estruturais e de qualidade entre projetos tradicionais e projetos baseados em blockchain**, com o propósito de **avaliar impactos mensuráveis da arquitetura blockchain (descentralização, custo de execução, imutabilidade, gas) em atributos de qualidade do código**, considerando métricas como complexidade, tamanho, modularidade e manutenibilidade.

A análise será conduzida sob a perspectiva de **pesquisadores, engenheiros de software e equipes de desenvolvimento que buscam compreender como tecnologias distribuídas influenciam a evolução, manutenção e qualidade do software**, no contexto de **projetos reais de código aberto escritos em linguagens típicas de desenvolvimento blockchain (Solidity, Rust/Substrate, Move) comparados a projetos tradicionais equivalentes**.

---

## 3.2 Objetivos específicos

**O1 – Caracterizar diferenças estruturais entre software tradicional e software blockchain**  
Identificar padrões estruturais e organizacionais que distinguem sistemas blockchain de sistemas tradicionais, incluindo tamanho, complexidade, modularização e dependências internas.

**O2 – Avaliar impacto das restrições do ambiente blockchain nas métricas de qualidade**  
Examinar como características como gas, imutabilidade, validações explícitas e custos de execução afetam medidas de complexidade, ramificações, lógica defensiva e redundância de código.

**O3 – Investigar correlação entre tipo de projeto e manutenibilidade**  
Avaliar se projetos blockchain apresentam menor índice de manutenibilidade, maior acoplamento ou maior necessidade de refatorações quando comparados a sistemas tradicionais.

**O4 – Analisar a evolução histórica dos projetos**  
Examinar diferenças no ritmo de evolução, quantidade de mudanças estruturais e incidência de refatorações profundas entre projetos blockchain e tradicionais.

**O5 – Derivar recomendações práticas para engenharia de software blockchain**  
Com base nas evidências empíricas, propor diretrizes para reduzir complexidade, melhorar manutenibilidade e apoiar decisões arquiteturais em sistemas blockchain.

---

## 3.3 Questões de pesquisa

### **O1 – Caracterizar diferenças estruturais**
- **Q1.1:** Projetos blockchain apresentam maior complexidade média de métodos/funções do que projetos tradicionais?  
- **Q1.2:** A modularização de contratos inteligentes difere significativamente da modularização de sistemas tradicionais?  
- **Q1.3:** O volume geral de código (LOC, arquivos, módulos) apresenta variações relevantes entre os dois grupos?

---

### **O2 – Impacto das restrições blockchain nas métricas**
- **Q2.1:** A existência de custos de execução (gas) aumenta o número de verificações, condicionais e lógica defensiva?  
- **Q2.2:** Smart contracts possuem maior complexidade ciclomática e profundidade de chamadas?  
- **Q2.3:** A imutabilidade gera maior repetição de lógica ou duplicação “controlada” em projetos blockchain?

---

### **O3 – Correlação entre tipo de projeto e manutenibilidade**
- **Q3.1:** A manutenibilidade medida por índices clássicos tende a ser menor em sistemas blockchain?  
- **Q3.2:** Módulos críticos em blockchain exigem maior esforço para modificação devido a dependências funcionais?  
- **Q3.3:** Há maior concentração de hotspots de manutenção em smart contracts?

---

### **O4 – Evolução histórica**
- **Q4.1:** Projetos blockchain apresentam menor frequência de modificações devido à imutabilidade?  
- **Q4.2:** Smart contracts requerem reescritas completas mais frequentemente do que sistemas tradicionais?  
- **Q4.3:** Atualizações de segurança tendem a impactar mais profundamente o código blockchain?

---

### **O5 – Recomendações práticas**
- **Q5.1:** Em quais cenários simplificar lógica blockchain impacta positivamente a manutenibilidade?  
- **Q5.2:** Existem limites (thresholds) de complexidade e tamanho que tornam um contrato difícil de manter?  
- **Q5.3:** Quais padrões arquiteturais se mostraram mais eficazes para manter a qualidade e modularidade do código blockchain?

---

## 3.4 Métricas associadas (GQM)

| Objetivo | Questão | Métricas associadas (mínimo 2) |
|----------|---------|--------------------------------|
| **O1** | **Q1.1 – Complexidade média** | - Complexidade ciclomática média (por função/método)<br>- WMC (Weighted Methods per Class) normalizado |
| **O1** | **Q1.2 – Modularização** | - Número de módulos/contratos<br>- Profundidade média das dependências internas |
| **O1** | **Q1.3 – Tamanho estrutural** | - LOC total<br>- Média de LOC por arquivo/módulo |
| **O2** | **Q2.1 – Lógica defensiva e validações** | - Contagem de condicionais por função<br>- Proporção de funções com validações explícitas (require/assert) |
| **O2** | **Q2.2 – Complexidade blockchain vs. tradicional** | - Complexidade ciclomática média por projeto<br>- Número médio de branches e loops por função |
| **O2** | **Q2.3 – Duplicação e repetição de lógica** | - % de LOC duplicada<br>- Número de clones ou trechos repetidos |
| **O3** | **Q3.1 – Manutenibilidade** | - Maintainability Index (MI)<br>- Debt Ratio (sonarqube-like) |
| **O3** | **Q3.2 – Esforço de modificação** | - Mudanças por módulo (commits por arquivo)<br>- Tamanho médio dos change sets |
| **O3** | **Q3.3 – Hotspots de manutenção** | - Arquivos/regiões com alta taxa de mudança<br>- Frequência de commits em módulos críticos |
| **O4** | **Q4.1 – Frequência de modificações** | - Commits por mês/ano<br>- Tempo entre releases |
| **O4** | **Q4.2 – Reescritas completas** | - Número de rewrites identificados<br>- Tamanho das refatorações profundas |
| **O4** | **Q4.3 – Impacto de updates de segurança** | - Mudanças por patch de segurança<br>- Variabilidade do tamanho do change set em correções |
| **O5** | **Q5.1 – Simplificação da lógica** | - Redução de complexidade após refatoração<br>- Redução de validações repetidas |
| **O5** | **Q5.2 – Thresholds de complexidade/tamanho** | - Limite de complexidade por função (ex.: CC > X)<br>- LOC por contrato acima de limiar pré-definido |
| **O5** | **Q5.3 – Padrões arquiteturais** | - Frequência de uso de proxies, bibliotecas ou módulos<br>- Acoplamento entre contratos (inter-contract calls) |


---

# 4. Escopo e contexto do experimento

## 4.1 Escopo funcional / de processo (incluído e excluído)
O experimento foca na análise estrutural de código fonte comparando softwares tradicionais e projetos baseados em blockchain (especialmente smart contracts em Solidity). O objetivo é avaliar diferenças mensuráveis relacionadas a complexidade, manutenibilidade, tamanho de código e densidade lógica.

**Incluído no escopo:**
- Código de produção de sistemas tradicionais (serviços backend, bibliotecas, APIs).
- Smart contracts e componentes principais de DApps executados na EVM.
- Extração de métricas estáticas (LOC, complexidade ciclomática, Maintainability Index, profundidade de aninhamento, número de funções).
- Comparação de snapshots fixos dos repositórios.

**Excluído do escopo:**
- Código gerado automaticamente (artefatos de build, bindings, stubs).
- Scripts de infraestrutura, CI/CD e arquivos de configuração.
- Testes automatizados, exceto como apoio pontual.
- Análises econômicas de gas, desempenho em rede ou comportamento dinâmico da blockchain.

---

## 4.2 Contexto do estudo (tipo de organização, projeto, experiência)
O estudo é conduzido em projetos open-source hospedados em plataformas públicas como GitHub e GitLab. O conjunto analisado inclui:

- Projetos tradicionais com histórico consolidado de manutenção.
- Smart contracts amplamente utilizados ou auditados, refletindo padrões reais do ecossistema blockchain.
- Equipes e comunidades descentralizadas, com contribuições distribuídas globalmente.

Os “participantes” diretos do estudo são os pesquisadores responsáveis por coletar, processar e interpretar as métricas. Os desenvolvedores dos projetos analisados atuam indiretamente, pois suas decisões de design e implementação constituem o objeto empírico observado.

---

## 4.3 Premissas
O experimento se apoia nas seguintes premissas:

1. Os repositórios selecionados permanecerão acessíveis e com histórico íntegro durante todo o processo.
2. Ferramentas de análise estática (Slither, lizard, radon, SonarQube) fornecerão métricas consistentes para diferentes linguagens.
3. Os commits e releases escolhidos representam versões estáveis e comparáveis entre os projetos.
4. Métricas tradicionais de engenharia de software (complexidade, LOC, MI) são bons proxies para avaliar qualidade estrutural, mesmo em contratos inteligentes.
5. A amostra de projetos blockchain e tradicionais é suficientemente diversificada para permitir comparações significativas.

---

## 4.4 Restrições
O experimento está sujeito a algumas restrições:

- Limitações de tempo, infraestrutura computacional e capacidade de processar múltiplos repositórios grandes.
- Restrições das ferramentas de análise, que variam em precisão dependendo da linguagem e do padrão de código.
- Possíveis mudanças em APIs de plataformas de hospedagem que limitem o acesso automatizado a dados.
- Ausência de intervenção formal em equipes ou mantenedores, reduzindo a possibilidade de complementar métricas com percepção qualitativa.

---

## 4.5 Limitações previstas
Alguns fatores podem afetar a generalização dos resultados:

- Projetos de blockchain frequentemente apresentam padrões de design muito específicos da EVM, o que pode limitar comparações diretas com sistemas tradicionais.
- A amostra pode não representar todo o ecossistema blockchain (por exemplo, diferentes padrões de smart contracts, linguagens alternativas como Vyper).
- Métricas podem ser influenciadas por estilo pessoal ou práticas de equipes, e não apenas por características intrínsecas do paradigma.
- Ferramentas podem introduzir erros de medição ao interpretar contratos inteligentes complexos.

---

# 5. Stakeholders e impacto esperado

## 5.1 Stakeholders principais
- Pesquisadores de engenharia de software interessados em métricas e qualidade aplicada a blockchain.
- Desenvolvedores de smart contracts e maintainers de DApps.
- Arquitetos e líderes técnicos responsáveis por padrões de desenvolvimento.
- Organizações e equipes que utilizam ou auditam contratos inteligentes.

---

## 5.2 Interesses e expectativas dos stakeholders
- **Pesquisadores:** evidências empíricas sólidas sobre diferenças estruturais entre software tradicional e blockchain.
- **Desenvolvedores:** orientações práticas para melhorar complexidade, legibilidade e segurança de contratos inteligentes.
- **Arquitetos:** insumos para definir guidelines de qualidade e modularização no desenvolvimento de DApps.
- **Gestores:** indicadores que justificam investimentos em refatoração, auditorias e melhoria contínua de contratos.

---

## 5.3 Impactos potenciais no processo / produto
- Identificação de áreas críticas (alta complexidade, baixa manutenibilidade) pode motivar mudanças arquiteturais.
- Projetos blockchain podem adotar práticas de desenvolvimento mais alinhadas a padrões consolidados de engenharia de software.
- No médio prazo, espera-se melhoria na previsibilidade de manutenção de smart contracts e redução de riscos estruturais.

---

# 6. Riscos de alto nível, premissas e critérios de sucesso

## 6.1 Riscos de alto nível
- Repositórios removidos, alterados ou com histórico incompleto.
- Falhas em ferramentas de análise, especialmente com sintaxes específicas de Solidity.
- Escalabilidade limitada para processar múltiplos projetos volumosos.
- Possibilidade de resultados inconclusivos por forte variabilidade entre projetos.

---

## 6.2 Critérios de sucesso globais (go / no-go)
O experimento será bem-sucedido se:

1. For possível coletar métricas válidas e consistentes para ambos os grupos (tradicional e blockchain).
2. A análise fornecer respostas claras ou informativas às questões de pesquisa.
3. Surgirem conclusões práticas aplicáveis por desenvolvedores, arquitetos e auditores de smart contracts.

Um **go** é motivado quando as evidências permitem identificar padrões claros.  
Um **no-go** ocorre caso os dados sejam inconsistentes, insuficientes ou inviáveis para análise estatística confiável.

---

## 6.3 Critérios de parada antecipada (pré-execução)
O experimento deve ser interrompido antes da execução caso:

- As ferramentas escolhidas não suportem de forma confiável os repositórios analisados.
- Haja indisponibilidade de infraestrutura mínima ou recursos computacionais.
- Repositórios blockchain ou tradicionais essenciais se tornem inacessíveis.
- Mudanças no escopo tornem necessário redesenhar todo o estudo.

---
