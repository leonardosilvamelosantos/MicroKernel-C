# Microkernel - Sistema Operacional Simples

## 📋 Descrição
Este projeto implementa um microkernel básico com duas versões: uma em JavaScript (moderna e educacional) e outra em C (mais próxima de um SO real). O sistema demonstra conceitos fundamentais de sistemas operacionais como gerenciamento de processos, memória, sistema de arquivos e comunicação entre processos (IPC).

## 🚀 Versões Disponíveis

### Versão JavaScript (Node.js)
Implementação moderna usando ES Modules, ideal para fins educacionais e demonstração de conceitos.

### Versão C
Implementação mais próxima de um SO real, com gerenciamento direto de memória e recursos de baixo nível.

## 🛠️ Funcionalidades

### Gerenciamento de Processos
- Criação e finalização de processos
- Escalonador Round-Robin com prioridades
- Estados de processo (pronto, executando, suspenso)
- Identificadores únicos (PID)
- Fila de processos prontos

### Gerenciamento de Memória
- Alocação e liberação dinâmica
- Sistema de lista livre (free list)
- Algoritmo best-fit para alocação
- Fusão de blocos adjacentes
- Controle de fragmentação

### Sistema de Arquivos
- Estrutura hierárquica de diretórios
- Operações básicas:
  - Criar diretórios (mkdir)
  - Criar/ler arquivos
  - Listar conteúdo (ls)
- Caminhos absolutos e relativos
- Manipulação de metadados

### Comunicação Entre Processos (IPC)
- Sistema de filas de mensagens
- Buffer circular para mensagens
- Timestamps em mensagens
- Múltiplas filas independentes
- Notificações assíncronas (versão JS)

### Drivers de Dispositivo
- Driver de Teclado
  - Buffer circular para entrada
  - Gerenciamento de eventos
- Driver de Display
  - Buffer de tela virtual
  - Controle de cursor
  - Rolagem automática

### Shell Interativo
- Interpretador de comandos
- Comandos disponíveis:
  - \`help\`: Lista comandos disponíveis
  - \`ps\`: Lista processos ativos
  - \`kill <pid>\`: Finaliza processo
  - \`ls [caminho]\`: Lista diretório
  - \`mkdir <caminho>\`: Cria diretório
  - \`write <arquivo> <conteudo>\`: Escreve arquivo
  - \`read <arquivo>\`: Lê arquivo

## 📦 Estrutura do Projeto

### Versão JavaScript
\`\`\`
src/
├── kernel.js              # Núcleo do sistema
├── process/              # Gerenciamento de processos
│   ├── process.js
│   └── processManager.js
├── memory/              # Gerenciamento de memória
│   └── memoryManager.js
├── filesystem/          # Sistema de arquivos
│   └── fileSystem.js
├── ipc/                 # Comunicação entre processos
│   └── messageQueue.js
├── drivers/            # Drivers de dispositivo
│   ├── keyboardDriver.js
│   └── displayDriver.js
└── shell/             # Interface de comando
    └── shell.js
\`\`\`

### Versão C
\`\`\`
src/
├── kernel.h            # Definições do kernel
├── kernel.c            # Implementação do kernel
├── process.h          # Interface de processos
├── process.c          # Implementação de processos
├── memory.h           # Interface de memória
├── memory.c           # Implementação de memória
├── filesystem.h       # Interface do sistema de arquivos
├── filesystem.c       # Implementação do sistema de arquivos
├── ipc.h              # Interface de IPC
├── ipc.c              # Implementação de IPC
├── shell.h            # Interface do shell
└── shell.c            # Implementação do shell
\`\`\`

## 🚀 Como Executar

### Versão JavaScript
1. Instale as dependências:
\`\`\`bash
npm install
\`\`\`

2. Execute o sistema:
\`\`\`bash
npm start
\`\`\`

### Versão C
1. Compile o projeto:
\`\`\`bash
make
\`\`\`

2. Execute o sistema:
\`\`\`bash
./microkernel
\`\`\`

## 💻 Exemplo de Uso

\`\`\`bash
> help
ps - Lista processos ativos
kill - Finaliza um processo: kill <pid>
ls - Lista conteúdo do diretório: ls [caminho]
mkdir - Cria diretório: mkdir <caminho>
write - Escreve em arquivo: write <arquivo> <conteudo>
read - Lê arquivo: read <arquivo>

> mkdir /usr/bin
Diretório criado: /usr/bin

> write /usr/bin/hello "Hello, World!"
Arquivo escrito: /usr/bin/hello

> read /usr/bin/hello
Hello, World!

> ls /usr/bin
hello
\`\`\`

## 🤝 Contribuindo
Contribuições são bem-vindas! Sinta-se à vontade para:
- Reportar bugs
- Sugerir novas funcionalidades
- Melhorar a documentação
- Enviar pull requests

## 📝 Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

## ✨ Agradecimentos
- Inspirado em conceitos clássicos de sistemas operacionais
- Desenvolvido como projeto educacional para demonstrar princípios de SO
- Implementações em JS e C para diferentes perspectivas de aprendizado