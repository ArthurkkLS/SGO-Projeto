# SGO — Sistema de Gestão Olímpica
---

## Sumário

- [Histórias de Usuário](#histórias-de-usuário)
- [Diagramas](#diagramas)
  - [Caso de Uso](#caso-de-uso)
  - [Pacotes](#pacotes)
  - [Classes](#classes)
  - [Componentes](#componentes)
  - [Implantação](#implantação)

---

## Histórias de Usuário

### Cadastro de competições

| ID | Como | Quero | Para que |
|----|------|-------|----------|
| US-01 | Organizador | Cadastrar uma nova competição com nome, data, horário e local | As provas estejam disponíveis para inscrição de atletas |
| US-02 | Organizador | Editar os dados de uma competição ainda não realizada | Correções de data ou local possam ser feitas antes do evento |
| US-03 | Organizador | Listar e filtrar competições por modalidade, data e status | Gerenciar a agenda do evento |

---

### Inscrição de atletas

| ID | Como | Quero | Para que |
|----|------|-------|----------|
| US-04 | Delegado de país | Inscrever um atleta em uma competição | Ele possa participar representando meu país |
| US-05 | Delegado de país | Consultar todas as inscrições dos meus atletas | Acompanhe em quais competições eles estão inscritos |
| US-06 | Delegado de país | Cancelar a inscrição de um atleta antes do início da competição | Possa substituí-lo se necessário |

---

### Alocação de locais

| ID | Como | Quero | Para que |
|----|------|-------|----------|
| US-07 | Organizador | Cadastrar locais com nome, capacidade e infraestrutura disponível | Possam ser alocados às competições |
| US-08 | Organizador | Alocar um local a uma competição com validação automática de conflito de horário | Dois eventos não ocupem o mesmo local ao mesmo tempo |
| US-09 | Organizador | Visualizar a agenda de um local por dia | Planeje a ocupação dos espaços |

---

### Controle de resultados

| ID | Como | Quero | Para que |
|----|------|-------|----------|
| US-10 | Juiz | Registrar o resultado de uma competição indicando o 1º, 2º e 3º lugares | As medalhas sejam atribuídas corretamente |
| US-11 | Juiz | Corrigir um resultado registrado com erro antes da publicação oficial | O placar reflita o desempenho real |
| US-12 | Espectador | Consultar os resultados publicados de cada competição | Acompanhe o desempenho dos atletas |

---

### Relatório de medalhas

| ID | Como | Quero | Para que |
|----|------|-------|----------|
| US-13 | Dirigente do COI | Visualizar o quadro de medalhas por país ordenado por ouro, prata e bronze | Acompanhe o desempenho das delegações |
| US-14 | Dirigente do COI | Filtrar o quadro de medalhas por modalidade ou período de datas | Analise o desempenho por segmento do evento |
| US-15 | Dirigente do COI | Exportar o relatório de medalhas em PDF ou CSV | Possa compartilhá-lo com outras organizações |

---

## Diagramas

### Caso de Uso

Representa os 5 atores do sistema — Organizador, Delegado de país, Juiz, Dirigente do COI e Espectador — e suas interações com os 15 casos de uso distribuídos nos cinco épicos.

<img src="https://github.com/ArthurkkLS/SGO-Projeto/blob/main/sgo/sgo_caso_de_uso.png" width="600"/>

---

### Pacotes

Organiza o sistema em quatro camadas: Apresentação, Aplicação, Domínio e Infraestrutura. Cada camada depende apenas da imediatamente abaixo, mantendo o acoplamento sob controle.

<img src="https://github.com/ArthurkkLS/SGO-Projeto/blob/main/sgo/sgo_diagrama_de_pacotes.png" width="600"/>

---

### Classes

Detalha as entidades do domínio (`Competicao`, `Atleta`, `Inscricao`, `Local`, `Resultado`, `Medalha`, `Pais`), os atores persistidos (`Usuario` e subclasses) e os serviços de domínio (`ValidadorConflito`, `GeradorRelatorio`).

<img src="https://github.com/ArthurkkLS/SGO-Projeto/blob/main/sgo/sgo_diagrama_de_classes.png" width="600"/>

---

### Componentes

Mostra a estrutura interna do backend em quatro níveis — Controllers, Services, Domain e Repositories — com interfaces explícitas entre cada nível para garantir baixo acoplamento. Inclui os componentes de exportação (PDF/CSV) e notificação (e-mail).

<img src="https://github.com/ArthurkkLS/SGO-Projeto/blob/main/sgo/sgo_diagrama_de_componentes.png" width="600"/>

---

### Implantação

Descreve a infraestrutura física distribuída em cinco zonas: dispositivo do usuário, DMZ (Nginx), zona de aplicação (frontend estático + API Spring Boot + servidor de exportação), zona de dados (PostgreSQL primário/réplica + Redis) e serviços externos (SMTP e object storage).

<img src="https://github.com/ArthurkkLS/SGO-Projeto/blob/main/sgo/sgo_diagrama_de_implantacao.png" width="600"/>
