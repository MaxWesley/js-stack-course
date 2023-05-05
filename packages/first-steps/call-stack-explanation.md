# Call Stack
É como o v8 (engine nodeJS) executa o código que escrevemos. É uma pilha de processamento que registra todas as funções do nosso arquivo executado.

Ao executar um código o javascript vai ler esse modulo de cima pra baixo declarando as funções e ao encontrar a primeira função invocada é quando a call-stack entra em ação, funcionando como uma pilha.

### Características
- A primeira função a entrar na pilha é a última a sair;
- A última função a entrar na pilha é a primeira a sair;
- O NODE não consegue executar duas call-stack ao mesmo tempo por ser *single-thread*. 

O fato de conseguir executar código assimcrono se dá por conta da Thread Pool que recebe essas *"funções bloqueantes"* para que o fluxo da call stack siga. Quando a "função bloqueante" se dá como terminada, a *thread pool* manda essa função-bloqueante para o Callback Queue e com o *Event Loop* fica esperando o processamento da call-stack finalizar para mandar o resultado da função de volta para a call-stack.