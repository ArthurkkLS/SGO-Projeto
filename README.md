# SGO - Sistema de Gestão Olimpica

## Histórias de usuários
### Cadastro de competições
US-01
Como organizador, quero cadastrar uma nova competição com nome, data, horário e local, para que as provas estejam disponíveis para inscrição de atletas.
Critérios de aceite: formulário valida campos obrigatórios; data/hora não pode ser no passado; local deve existir no cadastro; competição fica com status "aberta para inscrições".  

US-02
Como organizador, quero editar os dados de uma competição ainda não realizada, para que correções de data ou local possam ser feitas antes do evento.
Critérios de aceite: edição bloqueada após início da competição; alteração de local dispara revalidação de conflito de horário; histórico de alterações é salvo.  

US-03
Como organizador, quero listar e filtrar competições por modalidade, data e status, para que eu possa gerenciar a agenda do evento.
Critérios de aceite: filtros combináveis; resultado ordenável por data; exibe status (aberta, encerrada, realizada).  


### Inscrição de atletas
US-04
Como delegado de país, quero inscrever um atleta em uma competição, para que ele possa participar representando meu país.
Critérios de aceite: atleta só pode representar um país por modalidade; inscrição só permitida enquanto competição estiver aberta; confirmação enviada por e-mail.  

US-05
Como delegado de país, quero consultar todas as inscrições dos meus atletas, para que eu acompanhe em quais competições eles estão inscritos.
Critérios de aceite: visão por atleta e por competição; exibe país representado e status da inscrição.  

US-06
Como delegado de país, quero cancelar a inscrição de um atleta antes do início da competição, para que eu possa substituí-lo se necessário.
Critérios de aceite: cancelamento bloqueado após início; vaga liberada para nova inscrição; registro de cancelamento mantido no histórico.  

### Alocação de locais
US-07
Como organizador, quero cadastrar locais com nome, capacidade e infraestrutura disponível, para que possam ser alocados às competições.
Critérios de aceite: campo de capacidade obrigatório; local pode ter múltiplas modalidades compatíveis; status ativo/inativo.  

US-08
Como organizador, quero alocar um local a uma competição com validação automática de conflito de horário, para que dois eventos não ocupem o mesmo local ao mesmo tempo.
Critérios de aceite: sistema bloqueia alocação se local já estiver ocupado no horário; exibe lista de horários disponíveis; permite sobreposição apenas após confirmação manual de exceção.  

US-09
Como organizador, quero visualizar a agenda de um local por dia, para que eu planeje a ocupação dos espaços.
Critérios de aceite: visão de linha do tempo por local e dia; intervalos livres destacados; exportável em PDF.  

### Controle de resultados
US-10
Como juiz, quero registrar o resultado de uma competição indicando o 1º, 2º e 3º lugares, para que as medalhas sejam atribuídas corretamente.
Critérios de aceite: apenas atletas inscritos na competição podem ser selecionados; os três colocados devem ser atletas distintos; resultado só pode ser registrado após o horário de início da competição.  

US-11
Como juiz, quero corrigir um resultado registrado com erro antes da publicação oficial, para que o placar reflita o desempenho real.
Critérios de aceite: edição disponível apenas para resultados não publicados; requer justificativa; auditoria registra quem alterou e quando.  

US-12
Como espectador, quero consultar os resultados publicados de cada competição, para que eu acompanhe o desempenho dos atletas.
Critérios de aceite: acesso público sem login; exibe pódio com nome, país e medalha; filtrável por modalidade e data.  

### Relatório de medalhas
US-13
Como dirigente do COI, quero visualizar o quadro de medalhas por país ordenado por ouro, prata e bronze, para que eu acompanhe o desempenho das delegações.
Critérios de aceite: atualizado em tempo real após publicação de resultados; ordenação padrão: ouro desc → prata desc → bronze desc; exibe bandeira do país.  

US-14
Como dirigente do COI, quero filtrar o quadro de medalhas por modalidade ou período de datas, para que eu analise o desempenho por segmento do evento.
Critérios de aceite: filtros aplicáveis individualmente ou em combinação; quadro recalculado dinamicamente; opção de limpar filtros.  

US-15
Como dirigente do COI, quero exportar o relatório de medalhas em PDF ou CSV, para que eu possa compartilhá-lo com outras organizações.
Critérios de aceite: PDF com identidade visual do evento; CSV com colunas: país, ouro, prata, bronze, total; inclui data/hora de geração.
