# Lista de Exercício sobre Ranges e Funções Templates

Essa lista de exercícios tem por objetivo o desenvolvimento de uma biblioteca de funções **template** que operam sobre **ranges**, i.e. um par de ponteiros que definem um intervalo aberto-fechado sobre uma coleção. A programação com template ou _gabarito_ em C++ permite que você programe uma função sem especificar o tipo de dados sobre o qual a função vai trabalhar. Dessa forma é possível, por exemplo, criar uma _única_ função de ordenação que ordenda qualquer coleção de informações, como inteiros, strings, frutas e monstros.

Mais detalhes sobre cada função a ser implementada pode ser encontrada de maneira unificada no documento em PDF que se encontra [aqui](docs/lista_template.pdf).


# Resolvendo as Questões

Para resolver as questões segue as seguintes instruções:

1. Edite o arquivo `include/graal.h` para incluir seu código no corpo da função correspondente a cada questão da lista.
2. Quando finalizar ou se quiser tirar uma dúvida faça o _commit_ das alterações para o GitHub.
6. Pronto, agora você pode fazer _pull request_ em `feedback` ou abrir alguma _issue_, casa queira tirar dúvidas sobre algum exercício específico.

Ao final desse processo, todas as modificações preisam ser "_comitadas_" para o GitHub. O repo remoto no GitHub é o que será considerado como submissão do seu trabalho, além do envio do SIGAA.

Não esqueça de editar também o arquivo [`autor.md`](author.md) e incluir o seu nome e quais questões você conseguiu resolver.

Segue abaixo a árvore de diretórios do projeto, para facilitar a visualização dos arquivos.

```
.
├── author.md    <---------- VOCÊ DEVE INCLUIR SEU NOME NESSE ARQUIVO.
├── CMakeLists.txt
├── docs
│   └── lista_template.pdf
├── include
│   └── graal.h  <--------- ESTE É O ARQUIVO PARA INCLUIR SEU CÓDIGO.
├── README.md
└── tests
    ├── CMakeLists.txt
    ├── include
    │   └── tm
    │       ├── test_manager.cpp
    │       └── test_manager.h
    └── main.cpp  <--------- ESSE É O ARQUIVO COM OS TESTES, APENAS PARA CONSULTA.

5 directories, 9 files
```

# Compilando o Projeto

## Usando `cmake`

Nesta lista, todos os exercícios serão implementados na forma de uma função template.
Existem um arquivo `tests/main.cpp` onde os **testes unitários** para cada função foram implementados. Você pode olhar esse arquivo para entender como os testes foram projetados, mas você não deve alterá-lo.

A compilação e execução das questões pode ser feita usando `cmake`. A partir da pasta raiz do projeto faça:

```
cmake -S . -B build
```
para gerar os arquivos `Makefiles` do projeto. Em seguinda compile com:

```
cmake --build build --target run_all_tests
```
Esse comando ativa a compilação e, em seguida, executa os testes.

Alternativamente, se você desejar apenas compilar e não rodar os testes, utilize:
```
cmake --build build
```

A compilação gera um executável com o nome `run_tests` dentro da pasta `build`. No __windows__ esse executável fica na pasta `Debug`.

Logo após a compilação, para executar o programa com os testes use os comandos:

No linux:
```
cd build
./run_tests
```
No windows:
```
cd build
.\Debug\run_tests.exe
```

Caso você deseje repetir o processo de compilação, digamos, após uma alteração, basta executar o comando `make` dentro da pasta `build`.

## Usando Compilação Manual com `g++`

É possível compilar o programa "na mão" (i.e. sem o `cmake`) usando o `g++`. Para isso use o comando abaixo a partir do diretório raiz do projeto.
```
mkdir -p build
```
para criar a pasta `build` onde o executável será gerado, e
```
g++ tests/include/tm/test_manager.cpp tests/main.cpp -I./include -I./tests/include -o build/run_tests
```
para compilar e gerar o executável em `build`.

Neste caso, independente se é windows ou linux, o executável é gerado na pasta `build`, bastando executá-lo depois, como explicado acima.

# Considerações Finais

Não esqueça de incluir comentários no formato Doxygen para cada uma das funções, bem como comentários regulares informativos dentro do corpo da função.

A ausência de comentário será penalizada com a retirada de 1 ponto da sua nota (que vai de zero a dez).
