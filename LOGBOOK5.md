## LOOGBOOK 5


### Task 0: Environment Setup

- Primeiro usamos o comando "sudo sysctl -w kernel.randomize_va_space=0" para desativar a randomização do inicio dos endereços da "heap" e da "stack".


![](images/week5/adressrandomizer.jpg)


### Task 1: Getting Familiar with Shellcode

- Depois de compilarmos o Makefile presente na pasta "shellcode"
e corrermos o programa obtemos o seguinte: 

![](images/week5/a64.jpg)


### Task 2: Understanding the Vulnerable Program

- Rodamos este código "gcc -DBUF_SIZE=100 -m32 -o stack -z execstack -fno-stack-protector stack.c" para compilar o "stack.c" com a StackGuard  e "non-executable stack protections" desligados 
- Usamos "sudo chown root stack " para mudar a ownership do programa para a root
- Usamos "sudo chmod 4755 stack" para ligar o "SET-UID"

![](images/week5/task2.1.jpg)

### Task 3: Launching Attack on 32-bit Program (Level 1)

- Rodando o seguinte código:

![](images/week5/code.jpg)

- Obtemos os dados necessários para gerar o exploit:

![](images/week5/exploiy_python.png)

- Explicando o ataque:

1. Ingetamos a versão de 32 bits do shellcode
2. Inicializamos o ficheiro todo com NOPs 
3. Colocamos o código malicioso no final do payload
4. Com a informação que obtemos do "ebp" e "buffer" podemos criar um endereço suficientemente grande onde queremos retornar para encontrar os NOPs que nos levam ao shellcode

![](images/week5/buffer_overflow_worked.png)


- Através deste exploit podemos aceder ao terminal e utilizá-lo:

![](images/week5/terminal_funcional.png)

# CTF 3 D1

- Script usado na resolução

![](images/week5/scriptd1.jpg)


- Solução

![](images/week5/task1.jpg)






# CTF 3 D2

- Neste caso vamos usar o script de python fornecido com umas ligieiras alterações:
![](images/week5/script_python.jpg)

- Como no desafio 1 o buffer tem 20 bytes alocados o que faz com que ao dar scanf de 32 bytes haja overflow.
- Começamos por encher o buffer com 20 caracteres e nos restantes colocamos o endereço com a ordem inversa (por causa da stack) e o nome do ficheiro no fim.
- Ao rodar o scrip obtemos o seguinte:
![](images/week5/flag2.jpg)

