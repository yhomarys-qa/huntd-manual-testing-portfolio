# HUNTD (Web & Mobile) - Portfólio de Testes Manuais

## 📌 1. Visão Geral da Plataforma

A HUNTD é uma plataforma de recrutamento Web3 que conecta profissionais de tecnologia a empresas e startups, permitindo o gerenciamento de perfis, a busca de oportunidades e a comunicação entre candidatos e recrutadores.

O objetivo deste projeto foi avaliar o funcionamento dessas funcionalidades nos ambientes Web e Mobile, verificando se os fluxos correspondiam aos comportamentos esperados, respeitavam as regras de negócio e atendiam às necessidades de utilização da plataforma.

---

## 🔎 2. Análise e Definição da Estratégia

Antes de definir os cenários de teste, explorei a plataforma para compreender seu funcionamento, os perfis de usuários, as regras de negócio e os principais fluxos de utilização.

Analisei as funcionalidades disponíveis para identificar os comportamentos esperados e as condições que precisavam ser validadas. A partir dessa análise, defini os cenários considerando a importância de cada funcionalidade e os possíveis riscos associados ao seu funcionamento.

Analisei as regras de negócio para identificar os comportamentos esperados de cada funcionalidade e defini cenários positivos e negativos, considerando diferentes entradas de dados, condições-limite e possíveis inconsistências.

Considerei diferentes combinações de dados e condições de utilização para ampliar a cobertura das validações, priorizando os fluxos essenciais da plataforma e as funcionalidades com impacto direto na experiência dos usuários, e organizando os testes para os ambientes Web e Mobile de acordo com seus respectivos escopos.

Essa análise serviu como base para a elaboração dos casos de teste e para determinar quais comportamentos precisavam ser avaliados durante as execuções.

---

## 🧪 3. Execução e Validação

A partir dos comportamentos identificados e dos cenários definidos, elaborei casos de teste utilizando diferentes técnicas de teste de caixa-preta. Organizei os casos no TestRail para estruturar a cobertura, acompanhar as execuções e registrar os resultados obtidos.

As validações tiveram como foco verificar se o comportamento apresentado pelas funcionalidades correspondia às regras de negócio e aos resultados esperados.

- Elaborei casos de teste utilizando técnicas de particionamento de equivalência e análise de valor-limite.
- Organizei os casos de teste no TestRail, estruturando as execuções e acompanhando os resultados.
- Executei testes funcionais e Smoke na plataforma Web.
- Realizei validações no ambiente Mobile, considerando o escopo MVP.
- Verifiquei os comportamentos das funcionalidades por meio de diferentes entradas de dados, interações e condições de utilização.
- Comparei os resultados obtidos com os esperados para identificar divergências em relação aos critérios definidos.

---

## 🐛 4. Investigação e Documentação de Defeitos

Durante as execuções, concentrei a investigação nos comportamentos que apresentaram divergências em relação aos resultados esperados. Busquei reproduzir as falhas em condições específicas, compreender em quais situações ocorriam e reunir informações que permitissem documentar cada inconsistência.

- Investiguei comportamentos inesperados, reproduzindo as falhas por meio de sequências de passos e condições específicas.
- Comparei os resultados obtidos com os esperados para identificar divergências e compreender em quais situações ocorriam.
- Registrei **66 defeitos no Jira**, sendo 65 identificados na plataforma Web e 1 no ambiente Mobile.
- Documentei pré-condições, passos para reprodução, resultados esperados e obtidos, evidências e classificação de severidade e prioridade.
- Estruturei os relatos para apresentar informações claras e permitir a reprodução dos problemas identificados.

### 🐛 Registro de Defeitos — Jira

Durante as validações, foram identificados e registrados defeitos no Jira. Abaixo, apresento dois registros detalhados, selecionados para demonstrar as inconsistências encontradas nas versões Web e Mobile.

#### 🌐 WEB — BUG-001: Campo de senha aceita 2 caracteres em vez do mínimo de 8

**Pré-condições:**
1. O usuário está na página de cadastro ou configuração de senha da HUNTD Web.
2. Não existe uma sessão ativa na aba atual do navegador.

**Passos para Reprodução:**
1. Clicar no campo "New Password".
2. Inserir uma senha com apenas 2 caracteres (ex.: `12`).
3. Clicar no botão de envio ou em "Save/Create".

**Resultado Esperado:**

O sistema deve rejeitar a entrada e apresentar uma mensagem informando que a senha precisa conter no mínimo 8 caracteres.

**Resultado Obtido:**

O sistema aceita a senha de 2 caracteres e processa o formulário sem apresentar qualquer aviso de validação.

**Ambiente de Teste:**
- Sistema Operacional: Windows 11 Home
- Navegador: Google Chrome
- Resolução: 1920x1080

**Prioridade:** Alta

**Evidência:** [Visualizar Screenshot/Vídeo](https://imgur.com/a/uVNfP9v)

---

#### 📱 MOBILE — BUG-MOB-001: Campo de comunicação não aceita corretamente caracteres acentuados

**Pré-condições:**
1. O ambiente Mobile MVP está acessível.
2. O usuário acessou a funcionalidade de comunicação e abriu uma conversa ativa.

**Passos para Reprodução:**
1. Tocar no campo de entrada da conversa para abrir o teclado do dispositivo.
2. Digitar palavras que contenham vogais acentuadas, como "não", "você" e "avô".
3. Observar os caracteres apresentados no campo de entrada.

**Resultado Esperado:**

O campo deve aceitar e apresentar corretamente os caracteres acentuados, incluindo acentos agudos, circunflexos e til.

**Resultado Obtido:**

O campo apresenta falhas ao combinar determinadas teclas mortas, como til e circunflexo, com as vogais. Isso impede a digitação correta de palavras como "avô", "você" e "mão".

**Ambiente de Teste:**
- Dispositivo: Emulador Android (Medium Phone)
- Sistema Operacional: Android 14 (API 34)
- Navegador: Google Chrome Mobile
- Aplicativo: Mobile MVP

**Prioridade:** Média

**Evidência:** [Visualizar Screenshot/Vídeo](https://imgur.com/a/cZu96Ds)

---

## 🔄 5. Testes de Regressão

Nos testes de regressão, considerei a necessidade de verificar se as funcionalidades já existentes continuavam apresentando os comportamentos esperados, avaliando possíveis impactos em outros fluxos da plataforma. Para isso, organizei uma rodada de validação com os casos de teste existentes, buscando identificar falhas que pudessem comprometer o funcionamento do produto.

- Selecionei e executei casos de teste que abrangiam funcionalidades e fluxos existentes da plataforma Web.
- Reavaliei os comportamentos das funcionalidades considerando diferentes condições de utilização e regras de negócio.
- Analisei os resultados das execuções para identificar falhas funcionais e possíveis inconsistências em outros fluxos.
- Registrei os resultados no TestRail, permitindo acompanhar os casos aprovados, reprovados e a cobertura das validações realizadas.

---

## 📊 6. Resultados e Conclusão

Após consolidar os dados das execuções e os defeitos registrados, analisei os resultados para avaliar o comportamento das funcionalidades verificadas, identificar os principais problemas encontrados e compreender seus possíveis impactos na utilização da plataforma.

### 🌐 Resultados — Plataforma Web

| Ciclo de Teste | Executados | Aprovados | Reprovados |
|---|---:|---:|---:|
| Smoke Testing | 31 | 31 | 0 |
| Regressão Completa | 584 | 519 | 65 |
| **Total** | **615** | **550** | **65** |

- Smoke Testing: 100% de aprovação.
- Regressão: aproximadamente 89% de aprovação.
- 65 defeitos identificados no ambiente Web.

### 📱 Resultados — Mobile MVP

| Indicador | Resultado |
|---|---:|
| Casos Executados | 8 |
| Aprovados | 7 |
| Reprovados | 1 |
| Taxa de Aprovação | 88% |
| Taxa de Reprovação | 13% |

- 1 defeito identificado no ambiente Mobile.

### Indicadores Gerais do Projeto

- **623 execuções de teste** nos ambientes Web e Mobile.
- **66 defeitos identificados e documentados no Jira.**
- **557 casos aprovados** considerando todos os ciclos apresentados.
- **66 casos reprovados** considerando todos os ciclos apresentados.

### Principais Problemas Identificados

Durante as validações, foram identificadas inconsistências que poderiam comprometer aspectos importantes da utilização da plataforma, incluindo:

- Falha na validação da senha, permitindo o cadastro de valores inferiores ao mínimo estabelecido.
- Falha no campo de comunicação Mobile ao processar determinados caracteres acentuados.

Os resultados também demonstraram que, embora o Smoke Testing Web tenha apresentado 100% de aprovação, a execução mais abrangente de regressão revelou outras inconsistências funcionais que exigiam atenção.

Ao relacionar os resultados das execuções às regras de negócio e aos comportamentos esperados, foi possível avaliar as funcionalidades verificadas, identificar riscos de qualidade e documentar os pontos que necessitavam de investigação.

O projeto proporcionou experiência prática na definição de estratégias de teste, validação funcional, investigação de defeitos, gerenciamento de testes e avaliação da qualidade de aplicações Web e Mobile.

---

## 🛠️ Ferramentas e Metodologias

- **Gerenciamento de Testes:** TestRail (elaboração de casos de teste, organização das execuções e acompanhamento de métricas).
- **Gerenciamento de Defeitos:** Jira (registro, classificação e documentação de bugs).
- **Tipos de Teste:** Testes Funcionais, Smoke Testing, Testes de Regressão, Testes Positivos e Negativos.
- **Técnicas de Teste:** Caixa-Preta, Particionamento de Equivalência e Análise de Valor-Limite.
- **Metodologias:** Fundamentos de Scrum e Kanban e Ciclo de Vida de Testes de Software (STLC).

---

## 📂 Artefatos e Evidências de Testes

Os arquivos abaixo disponibilizam os casos de teste elaborados e os registros das execuções realizadas durante o projeto.

### 📋 1. Casos de Teste

- 🌐 **[Visualizar Casos de Teste Web](huntd-web.csv)**
- 📱 **[Visualizar Casos de Teste Mobile](huntd-mobile.csv)**

### 🔍 2. Histórico de Execuções (Test Runs)

- 🧪 **[Test Run 1: Smoke Test - Web (100% aprovados)](test_run_1__smoke_test___web.csv)**
- 🧪 **[Test Run 2: Regressão Completa - Web (89% aprovados)](test_run_2__full_regression___web.csv)**
- 📱 **[Test Run 4: Execução Completa - Mobile MVP (88% aprovados)](test_run_4__full_execution___mobile_mvp.csv)**
