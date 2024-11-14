# AWS

1. AWS: Amazon Web Services (AWS) é uma plataforma de computação em nuvem oferecida pela Amazon, que fornece uma vasta gama de serviços como armazenamento, computação, análise de dados e redes. Utilizado por empresas de todos os tamanhos, o AWS oferece infraestrutura escalável e flexível, permitindo que as aplicações possam crescer em escala e eficiência. Os serviços AWS são divididos em várias categorias, como armazenamento (S3), banco de dados (RDS), rede (VPC), e automação de fluxos de trabalho (Step Functions), entre outros.

---

2. Funções de etapa da AWS: O AWS Step Functions é um serviço gerenciado que facilita a coordenação e a orquestração de microserviços e processos de fluxos de trabalho complexos de forma visual e lógica. Ele permite a criação de fluxos de trabalho baseados em estado para automatizar processos e aplicativos, facilitando a criação de fluxos de trabalho que dependem de uma série de etapas interdependentes. O Step Functions é ideal para aplicações que necessitam de escalabilidade e resiliência, pois permite a definição de etapas em uma sequência lógica. Cada etapa é chamada de estado, e o fluxo de trabalho pode ser criado de forma visual no Workflow Studio , o que facilita a compreensão e o monitoramento dos processos.

---

3. Transições de Estado para AWS: As transições de estado são as mudanças que ocorrem de uma etapa (estado) para outra em um fluxo de trabalho. No Step Functions, cada estado representa uma atividade específica, e o controle de transição define como um estado está conectado ao próximo, criando uma sequência do fluxo de trabalho. Essas transições são definidas para:
- Executar ações específicas.
- Solicitar serviços.
- Decidir a próxima etapa com base nas condições específicas.
- Controlar o fluxo por meio de lógica condicional (como loops e bifurcações).
- Isso é essencial para garantir que o fluxo de trabalho siga a sequência correta, lidando com erros e garantindo a execução bem-sucedida dos processos.

---

4. Fluxos de trabalho padrão: Os Standard Workflows são fluxos de trabalho que oferecem alta durabilidade e resiliência, sendo específicos para operações de longa duração e complexidade. Eles têm a capacidade de persistir dados ao longo de uma execução e de fazer vários testes automaticamente em caso de falhas. Esse tipo de fluxo de trabalho permite que você acompanhe cada etapa individualmente e visualize falhas e sucessos no monitoramento. As principais características dos fluxos de trabalho padrão incluem:
- Persistência dos dados de estado.
- Capacidade de execução de até 1 ano.
- Resiliência contra falhas e alta capacidade de tolerância.
- Tentativas automáticas de execução de etapas em caso de falha.

---
  
5. Fluxos de trabalho expressos: Os Express Workflows são otimizados para cargas de trabalho de curta duração e de alta velocidade. Eles são usados ​​principalmente para tarefas que requerem execuções rápidas e possuem menor duração, como processamento de dados em tempo real. A arquitetura desses fluxos de trabalho é menos durável do que os fluxos de trabalho padrão, pois são específicos para escalabilidade massiva e menor custo.
- Características principais:
Execuções rápidas e otimizadas para curta duração (em segundos). Ideal para fluxos que não necessitam de durabilidade prolongada dos dados de estado. Menor custo em comparação com fluxos de trabalho padrão. Capacidade de lidar com uma quantidade massiva de execuções simultâneas.

---

6. Diferenças entre fluxos de trabalho padrão e expresso:
- Fluxos de trabalho padrão: Duração da Execução até 1 ano; Resiliência	Alta, com esforço automático; Persistência de Dados	Total, com histórico detalhado; Escalabilidade limitada, mas tolerante a falhas; Cobrança baseada em transições de estado.
- Fluxos de trabalho expressos: Duração da Execução	até 5 minutos; Menos resiliente; Não há histórico completo; Escalabilidade alta, para cargas em tempo real; Cobrança baseada no tempo de execução.

---

7. Cobrança do AWS Step Functions: O modelo de cobrança do AWS Step Functions varia de acordo com o tipo de fluxo de trabalho escolhido:
- Fluxos de trabalho padrão : a cobrança é baseada na quantidade de transições de estado. Cada transição tem um custo associado, o que significa que quanto mais complexo o fluxo (com mais estados), maior será o custo.
- Express Workflows : a cobrança é baseada no tempo de execução em milissegundos, e na quantidade de memória utilizada para cada execução. Esse modelo é mais adequado para fluxos de trabalho de curta duração e alta frequência.
Além disso, em ambos os tipos, podem ocorrer cobranças adicionais pelos serviços AWS utilizados dentro do fluxo de trabalho, como invocações de Lambda ou chamadas de API para outros serviços da AWS.

---

8. Exemplos de uso do AWS Step Functions: O Step Functions pode ser usado para:
- Processamento de Dados em Lote : criação de pipelines de processamento de dados que invocam uma série de tarefas em sequência, como análise e transformação de dados.
- Processamento de Imagens/Vídeos : de forma cooperativa de tarefas para processamento de arquivos de mídia em larga escala, com diferentes etapas de processamento, como redimensionamento e transcodificação.
- Fluxos de Aprovação : implementação de fluxos de trabalho de aprovação para processos como contratados, onde cada etapa precisa de uma aprovação ou revisão.
- Orquestração de Microserviços : orquestração de múltiplos serviços, como API Gateway, Lambda e DynamoDB, para criar fluxos de trabalho que automatizam processos de negócios.

---

9. Língua dos Estados da Amazônia (ASL): A Amazon States Language (ASL) é uma linguagem de definição de estado usada para criar fluxos de trabalho no AWS Step Functions. Escrita em formato JSON, a ASL define como cada estado se comporta, o que inclui:
- O tipo de estado (ex: Task, Choice, Parallel).
- Parâmetros de entrada e saída.
- Tratamento de abordagem e condições de transição.
- Cada estado é configurado por propriedades específicas, como “Tipo”, “Recurso” e “Próximo”, permitindo a definição específica das transições e condições de execução no fluxo de trabalho.

---

10. Breve Tutorial Passo a Passo da Criação de um Template no Workflow Studio: Tutorial básico para criar um modelo de fluxo de trabalho no Workflow Studio do AWS Step Functions:
- Acessar o AWS Step Functions : Entre na sua conta AWS e vá ao console do Step Functions.
- Criar um Novo Workflow : Clique em “Criar máquina de estado” e selecione “Projete seu fluxo de trabalho visualmente” para abrir o Workflow Studio.
- Selecionar o Tipo de Fluxo de Trabalho : Escolha entre Fluxo de Trabalho Padrão ou Expresso de acordo com a necessidade.
- Adicionar Estados ao Workflow : No painel visual, clique em “Adicionar estado” e selecione o tipo de estado (ex: Tarefa, Paralelo). Configure o estado com a função AWS Lambda ou outro recurso que deseja invocar.
- Configurar Transições : Defina as transições entre estados. No Workflow Studio, arraste e conecte os estados para organizar a sequência desejada.
- Configure condicionais, se necessário, usando Choice States.
- Testar o Workflow : Salve o template e use a opção de teste no console para verificar a execução e corrigir erros.
- Deploy e Monitoramento : Quando estiver satisfeito, clique em “Deploy”. O AWS Step Functions oferece métricas e logs para monitorar o status e o desempenho do fluxo de trabalho.

---
