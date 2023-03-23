# SRC-P08 (Requisições HTTP e HTTPS)

Este projeto é uma demonstração reproduzível do conceito de requisições,
HTTP e HTTPs para que você mesmo possa fazer o trabalho na linha de comando.

Este projeto é para alunos da disciplina SI01033 (Segurança em Redes de Computadores) 
do Curso de Sistemas de Informação da Unifesspa, que querem testar ferramentas 
de criptografia para  reproduzir os próprios resultados ou brincar com o conceito 
para criar variações dos resultados a serem obtidos.

## Ferramentas

Instalar a ferramenta *netcat* via terminal do Linux:

    $ sudo apt update
    $ sudo apt install netcat

Com a ferramenta *netcat* instalada, ela pode ser utilizada da seguinte forma:

    $ nc <endereco_ip> <porta>

Onde, <endereco_ip> deve ser substituído pelo endereço IP do servidor e <porta>
pelo número da porta onde roda o serviço Web, conforme o exemplo a seguir:

    $ nc 200.129.138.99 80  


### Testando uma requisição HTTP

Para testar uma requisição HTTP é necessário abrir uma conexão TCP com 
o servidor de destino, por meio do aplicativo *netcat*, e posteriormente
realizar uma requisição HTTP conforme exemplo abaixo:

    $ nc 200.129.138.99 80
    GET / HTTP/1.1
    Host: coordenador.fadesp.org.br

Após digitar o texto acima, duas linhas em branco devem ser inseridas 
(com a tecla ENTER), para informar que já finalizamos a requisição.

Em seguida, o servidor deve devolver uma resposta, conforme exemplificado
na figura `Imagem1.png`, abaixo.

![Imagem1](/Imagem1.png)

### Testando uma requisição HTTP

Para testar uma requisição HTTPS é necessário abrir uma conexão TCP, 
porém neste caso utilizaremos um aplicativo chamado *openssl*, que será
responsável por estabelecer o tunel SSL/TLS.



### Testando o Modo ECB

Para alterar o modo de cifragem para *CBC*, simplemente basta mudar o algoritmo 
para *aes-128-cbc", e alterar o arquivo de saída para *Tux.body.cbc*.

    head -n 3 Tux.ppm > Tux.header
    tail -n +4 Tux.ppm > Tux.body
    openssl enc -aes-128-cbc -nosalt -pass pass:"rob" -in Tux.body -out Tux.body.cbc
    cat Tux.header Tux.body.cbc > Tux.ecb.ppm    


## Conclusão

O objetivo deste projeto é simplesmente para propósitos educacionais, 
para permitir ao discente, entender as diferenças entre os modos *ECB* e *CBC*.
