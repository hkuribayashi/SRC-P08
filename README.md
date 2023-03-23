    # Projeto SRC-P08

    Este projeto é uma demonstração reproduzível dos conceitos de requisição HTTP e HTTPS

    Este projeto é para alunos da disciplina SI01033 (Segurança em Redes de Computadores) 
    do Curso de Sistemas de Informação da Unifesspa, que querem testar ferramentas 
    de criptografia para  reproduzir os próprios resultados ou brincar com o conceito 
    para criar variações dos resultados a serem obtidos.

    ## Ferramentas

    O algoritmo de criptografia mais comum, AES, usa uma *cifra de bloco* com
    blocos de 128 bits.

    Uma *cifra de bloco* sempre criptografa o mesmo conteúdo da mesma maneira, dado
    a mesma chave (processo determinístico).

    Podemos demonstrar isso criptografando imagens de desenhos animados. Figuras/Desenhos 
    tendem a ter regiões onde todas as cores são as mesmas e, portanto, irão gerar a mesma 
    criptografia ao usar uma cifra de bloco.

    A figura mais famosa por demonstrar isso, de onde vem esse problema
    seu nome, é o mascote pinguim Linux conhecido como "Tux" (autoria de Larry Ewing 
    lewing@isc.tamu.edu [Referência](https://commons.wikimedia.org/wiki/File:Tux.png)):

    ![Tux](/Tux.png)

    Observe como grandes regiões do desenho são completamente brancas (0xFFFFFF)
    ou completamente preto (0x000000).

    Na imagem abaixo, nós o criptografamos usando o modo ECB.

    ![Tux-ecb](/Tux.ecb.png)

    Como você pode ver, a imagem ainda é reconhecível como um pinguim.

    ### Testando o Modo ECB

    O objetivo deste projeto não é descrever o pinguim ECB, mas ajudar o discente reproduzi-lo.

    Começamos com o arquivo `Tux.ppm`. Ele está em um formato bruto descompactado, conhecido 
    como PPM.

    O formato de imagem PPM tem quatro campos de texto seguidos por dados binários:
    1. O tipo de arquivo; 
    2. A largura em pixels; 
    3. A altura em pixels; e 
    4. O número de cores (geralmente 255 ou 256 para cor de 8 bits).

    O restante do arquivo são dados binários contendo a imagem bruta e descompactada.

    Podemos recuperar o cabeçalho deste arquivo fazendo:

        $ head -n 3 Tux.ppm
        P6
        265 314
        255

    A


    ## Conclusão

    O objetivo deste projeto é simplesmente para propósitos educacionais, 
    para permitir ao discente, entender as diferenças entre os modos *ECB* e *CBC*.
