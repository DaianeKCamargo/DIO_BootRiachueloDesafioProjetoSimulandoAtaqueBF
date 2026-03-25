# DIO BOOTCAMP RIACHUELO CIBERSEGURANÇA

## Desafio de Projeto
Implementar, documentar e compartilhar um projeto prático utilizando Kali Linux e a ferramenta Medusa, em conjunto com ambientes vulneráveis (por exemplo, Metasploitable 2 e DVWA), para simular cenários de ataque de força bruta e exercitar medidas de prevenção.

- Configurar o ambiente: duas VMs (Kali Linux e Metasploitable 2) no VirtualBox, com rede interna (host-only).
- Executar ataques simulados: força bruta em FTP, automação de tentativas em formulário web (DVWA) e password spraying em SMB com enumeração de usuários.
- Documentar os testes: wordlists simples, comandos utilizados, validação de acessos e recomendações de mitigação.

--- 

## Documentação do Teste

### Configuração do Ambiente
Foi criado um cenário fictício utilizando uma VM Metasploitable 2 como o alvo da invasão, e instalado uma VM Kali Linux ferramenta que será utilizado para fazer a invasão, ambas suas configurações foram utilizadas a rede "VirtualBox Host-Only Ethernet Adapter", a qual permitirá que a rede esteja na mesma faixa. Ambas utilizações, por meio de segurança, todo o teste será feito por uma VM onde foi criado todo um cenário para estar sendo feito os testes, não comprometendo um computador real.

### Ataques
**Situação1:** Tentativa de Ataque de Força Bruta em FTP <br>
**Ação:** 
- Confirmei se está tudo certo com a conexão do meu alvo, enviando 4 pct de transmissão, sendo assim obtive o retorno dos 4, ou seja, minha conexão foi efetuada. [img01]
- Pra efetuar o ataque é necessário uma wordlist, a qual utilizarei a mesma que foi criada na aula, nome dos arquivos: usuários - user.txt e senhas - pass.txt
- Antes de tudo, iremos verificar as portas que estão abertas e versão sistema, utilizando o nmap. [img02]
- Testar se a serviço ftp está aceitando conexões, retorno deu 220 OK. [img03]
- Tentiva de descobrir o usuário e senha por meio da wordlist utilizando a ferramenta medusa e o serviço FTP. Aqui ele pega os usuarios e senha do arquivo fornececido e faz uma analise combinatória de tenativas e erros, quando acha ele aponta 'account found'  [img04]
- Após achar o usuario e senha de login, se tem o acesso da maquina [img05]

**Situação2:** Tentiva de descobrir o acesso de contas dentro do alvo, utilizando a o ataque Password Spraying e o serviço SMB. <br>
**Ação:** 
- Após fazer todo o processo de reconhecer as portas, identificar usuario e senha do servidor alvo, foi feito uma enumeração dos usuário que o alvo possui. [img06]
- Criar uma wordlist dos usuários encontrados e oujtra wordlist con senhas possiveis. Utilizei a lista que foi criada em aula. nome dos arquivos: usuários - smb_users.txt e senhas: senhas_spray.txt, ele irá fazer a analise combinatória de tentativa e erros, após um usuário e senha forem encontrados ele aparecerá ACCOUNT FOUND e ainda mostra o acesso admin da conta. [img07]
- Teste se o acesso é mesmo de admin, apareceu uma lista de compartilhamento, confirmação do acesso admin. [img08] 

**Situação3:** Automação de tentativas em formulário web, será utilizado a página de login da DVWA onde simulará uma página real da web [img09] <br> 
**Ação:** 
- Começa fazendo a analise do site para entender um pouco sobre a página, utilizando o "inspecionar" do navegador, em network, foi feito uma tentativa erronea de logar, a qual nos mostrará os parametros utilizando pelo backend e a mensagem de resposta retornada ao apresentar um erro, essa mensagem será o indicador da ferramenta medusa quando houver falhas. [img10]
- Utiliza uma wordlist também neste caso, como é apenas uma simulação foi se utilizado o mesmo arquivo Situação 1.
- PROBLEMA: Na aula ela apresenta o ataque com o medusa, mas nos meus teste não obtive sucesso SOLUÇÃO achada, utilizei o ataque com o hydra a qual sim obtive o retorno esperado. [img11]

**Como evitar um ataque de Força Bruta** <br>
Para uma evitar de ser alvo de uma ataque de força bruta, alguns procedimentos de segurança devem ser tomados:
- Utilizar senha com no mínimo 10 caracteres contendo letras (maíscula e minúscula), números e caracteres especiais.
- Não utilizar a mesma senha em outras contas, manter cada uma com uma senha diferente.
- Habilitar MFA.
Com esses mínimos de cuidado, já consegue ser evitado de ser vítima de uma ataque como este.


