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
Situação: Tentativa de Ataque de Força Bruta em FTP
Ação: 
- Confirmei se está tudo certo com a conexão do meu alvo, enviando 4 pct de transmissão, sendo assim obtive o retorno dos 4, ou seja, minha conexão foi efetuada. [img01]
- Pra efetuar o ataque é necessário uma wordlist, a qual utilizarei a mesma que foi criada na aula, nome dos arquivos: usuários - user.txt e senhas - pass.txt
- 
