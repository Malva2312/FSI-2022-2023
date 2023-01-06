# Trabalho realizado na Semana #3

## CTF Semana 3

- Encontrámos a FLAG do desafio na página das "RULES".
- Copiamos a FLAG.
- Colocamos a FLAG na caixa de texto do "Sanity Check".
- Encontrámos a FLAG e subtemos, obtendo assim a confirmação da resolução do problema.

## CVE-2021-26858

### Identificação

- Esta vulnerabildade é do tipo "Post-Authentication Arbitrary File Writer".
- É um tipo de falha de segurança que permite a um atacante carregar ficheiros maliciosos para um servidor quando já autenticado.
- Afeta as versões 2013, 2016 e 2019 do Microsoft Exchange.


### Catalogação

- Invasões detectadas, pelo menos, desde janeiro de 2021.
- Métricas de pontuação de base (CVSS 3.0): 7.8 (HIGH).
- Este CVE foi publicado pela Microsoft.



### Exploit

- Faz parte de um encadeamento de ataques, iniciados com uma conexão não confiável para a porta 443 do servidor do Exchange (ProxyLogon).
- O acesso é garantido através de outras vulnerabiladdes (CVE-2021-26855 e CVE-2021-26857).
- Os operadores do HAFNIUM implantaram web shells no servidor comprometido.
- As Web shells podem permitir invasores roubar dados e executar ações maliciosas. 

escrever relatos de utilização desta vulnerabilidade para ataques bem sucedidos e/ou potencial para causar danos
### Ataques

- Os operadores do HAFNIUM conseguiram descarreagar o catálogo de endereços do Exchange offline de sistemas comprometidos, que contêm informações sobre uma organização e sobre os seus utilizadores.


