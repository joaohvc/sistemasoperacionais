Responder o questionário abaixo em seu GitHub (individual). Coloque as perguntas e respostas.

Exercícios Teóricos – Processos

1. Qual a diferença entre programa e processo?
   Programa: Conjunto de instruções armazenadas em disco (entidade passiva).
   Processo: Programa em execução, com estado, memória e recursos alocados (entidade ativa).
2. Quais são os estados de um processo e quando ocorrem as transições?
   
3. O que contém um Process Control Block (PCB)?
   O PCB (Process Control Block) é como a “ficha de identidade” de cada processo. Ele guarda todas as informações               necessárias para o sistema operacional pausar e retomar o processo depois.E oque contém um PCB é a indentificaçao do         processo, estado do rocesso, contador de programa, contexto de registradores da CPU, informaçoes de escalonamento e          informaçoes de gerenciamento de memorias
4. O que acontece com os recursos de um processo quando ele termina?
   A memoria alocada ao processo é liberada, Arquivos abertos sao fechados, Dispositivos que estavam sendo usados sao           liberados, A entrada do processo na tabela do SO é removida ou marcada como "terminada".
5. Qual a diferença entre fork() e exec() no UNIX?
   O fork() cria um novo processo filho a partir do processo atual pai,sendo o processo filho sendo quase uma copia do          pai(mesma memoria,mesmos aquivos abertos e mesmo registrados).
   O exex() substitui o codigo e dados do processo atual por um novo programa.Ou seja ,o processo nao cria um novo, ele vira    outro.Existindo varias versoes como execl,execv e execvp.
6. Como funciona a hierarquia de processos em UNIX?
    No UNIX/LINUX todos processos tem uma hierarquia PAI-FILHO, formando uma arvore de processos. Primeiro sendo o Processo      Inicial, Processos Filhos, Relação PAI-FILHO, Arvore De Processos.
7. Compare memória compartilhada e troca de mensagens (IPC).
    Memoria Compartilhada:Funciona quando dois ou mais processos acessas uma mesma area de memoria.Sendo suas vantagens:É muito rapida(acesso direto a memoria), Permite transferencia de grandes volumes de dados sem copia.                              Troca De Mensagens (IPC): Funciona com o processos de enviar mensagens entre si via sistema                                  operacional(FILAS,PIPES,SOCKETS).Sendo suas vantagens:
8. Cite exemplos de chamadas de sistema usadas em IPC.
    1°:Pipes e FIFOs 2°:Memoria Compartilhada (System V IPC) 3°:Filas de Mensagens 4°:Semaforos 5°:Sinais.
9. Por que é importante que o sistema operacional faça gerenciamento de processos?
    Permite que varios processos rodem ao mesmo tempo, mesmo que haja apenas uma CPU, usando escalonamento e troca de            contexto, Isolamento e segurança, Gerenciamento de recursos. Coordenação e comunicação, Estabilidade do sistema.
10. Explique a diferença entre processos independentes e processos cooperativos.
    Processos Independentes: Eles nao dependem de outros processos, nao compartilham dados nem recursos com outros               processos, sua execuçao nao afeta nem afetada por outros processos.                                                          Processos coorperativos Eles dependem de outros processos para realizar tarefas, compartilham dados, memoria ou              recursos, precisam coordenar açoes para evitar conflitos.
11. O que é um processo zumbi em UNIX/Linux?
    Um processo zumbi em UNIX/Linux é um processo que já terminou sua execução, mas que ainda permanece na tabela de processos do sistema porque o processo pai ainda não coletou o seu status de término (via chamada      de sistema wait() ou waitpid()).
12. Explique a diferença entre chamadas bloqueantes e não bloqueantes em IPC.
    Em IPC (Inter-Process Communication), ou Comunicação entre Processos, a diferença entre chamadas bloqueantes e não bloqueantes está no comportamento do processo emissor/receptor quando a operação de comunicação      não pode ser imediatamente concluída.
13. Qual a diferença entre processo pesado (process) e thread (processo leve)?
    Processo pesado:É a unidade de execução independente no sistema,tem seu próprio espaço de endereçamento (memória isolada),possui seus próprios recursos alocados (descritores de arquivos, pilha, registradores,        etc.),A comunicação entre processos (IPC) é necessária para troca de dados (pipes, filas, sockets etc.),A criação de um processo é relativamente cara (demora mais, consome mais recursos).                                                       Thread(Processo leve):Também é uma unidade de execução, mas dentro de um processo,compartilha o espaço de endereçamento do processo pai e os mesmos recursos (memória global, arquivos abertos etc.),tem apenas seu próprio contador de programa, registradores e pilha,a comunicação entre threads é muito mais rápida, já que compartilham memória
14. Por que sistemas operacionais multiprogramados precisam de troca de contexto (context switch)?
    Um sistema multiprogramado tem como objetivo executar vários processos "ao mesmo tempo" (concorrência). Mas, na prática, o processador só consegue executar uma instrução por núcleo de CPU de cada vez.Para dar a ilusão de paralelismo e garantir que todos os processos recebam tempo de CPU, o sistema precisa alternar a execução entre processos.Essa alternância é feita pela troca de contexto (context switch).
15. Cite vantagens e desvantagens da comunicação via memória compartilhada.
    Velocidade alta – não há cópia extra de dados entre processos; todos acessam a mesma área de memória.
Baixa sobrecarga – após a configuração inicial, o kernel quase não participa da comunicação (diferente de pipes, mensagens ou sockets).
Ideal para grandes volumes de dados – muito mais eficiente que mandar dados grandes por pipe/fila.
Flexibilidade – os processos podem estruturar os dados da forma que quiserem dentro da memória.
