# Sistema de Reservas de Hotel

## Sumário:
- [Introdução](#introdução)
- [Como Executar o Projeto](#como-executar-o-projeto)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Funções e Classes](#funções-e-classes)

## Introdução <a name="introdução"></a>

Bem-vindo ao nosso projeto de Sistema de Reservas de Hotel. Este software foi desenvolvido para simplificar a gestão de reservas, check-ins e check-outs em um hotel. Oferecemos uma interface fácil de usar para realizar essas operações de forma eficiente, proporcionando uma visão clara do status dos quartos e facilitando o controle das reservas.

## Como Executar o Projeto <a name="como-executar-o-projeto"></a>

### Requisitos:
1. Baixe o arquivo executável (`main.exe`) do [último release](https://github.com/CSeisOssos/Logica_de_programacao_C/releases/latest).
2. Certifique-se de ter um ambiente Windows para executar o arquivo executável.

### Executando o Projeto:
1. Execute o arquivo `main.exe`.
2. Siga as instruções na interface do console para interagir com o sistema.

## Estrutura do Projeto <a name="estrutura-do-projeto"></a>

O projeto está organizado da seguinte forma:
- `hotel.h`: Contém as definições de estruturas e protótipos de funções utilizadas no projeto.
- `hotel.c`: Implementações das funções definidas em `hotel.h`.
- `main.c`: Função principal que interage com o usuário, chamando as funções do hotel.

## Funções e Classes <a name="funções-e-classes"></a>

### Função: `fazerReserva`
Agora lidaremos com as funções implementadas em hotel.c, e aqui estão elas:

```c
void criarPastaSaves();
Cria a pasta saves no diretório raiz do projeto, pasta utilizada para guardar os arquivos importados e exportados.

```c
void inicializarHotel(Reserva hotel[NUM_ANDARES][NUM_QUARTOS_POR_ANDAR]);
Essa função zera todos os valores das reservas ao iniciar o programa para que caracteres aleatórios e bugs não
Apareçam durante a execução do programa, isso é necessário para setar todos os valores dos quartos como '0'.

```c
void exportarReservas(Reserva hotel[NUM_ANDARES][NUM_QUARTOS_POR_ANDAR]);
Essa função salva todas as reservas existentes na memória para serem carregadas posteriormente.
Eu criei essa função caso o PC do hotel tenha que ser desligado, ou tirado para reparos, coisas assim.

```c
void importarReservas(Reserva hotel[NUM_ANDARES][NUM_QUARTOS_POR_ANDAR], int *totalReservas);
Essa função carrega informações de reservas prévias salvas em um arquivo externo dentro da pasta Save.
Não se preocupe se você não tiver uma pasta Save, a pasta é criada junto com a primeira execução do programa.
A função lê o arquivo e coloca os dados nas variáveis necessárias.

```c
void fazerReserva(Reserva hotel[NUM_ANDARES][NUM_QUARTOS_POR_ANDAR], int* totalReservas);
Essa função verifica se há espaço para mais uma reserva, se as entradas do andar e do quarto são válidas 
E se sim, a reserva é feita utilizando um ponteiro que muda o valor do quarto de 0 para 1.

```c
void realizarCheckIn(Reserva hotel[NUM_ANDARES][NUM_QUARTOS_POR_ANDAR]);
Essa função realiza o check in do cliente, mudando o status da reserva de 0 para 1 caso o quarto esteja
Livre e perguntando ao usuário quantos dias ele passará, caso ele não esteja livre, a reserva não é feita.

```c
void realizarCheckOut(Reserva hotel[NUM_ANDARES][NUM_QUARTOS_POR_ANDAR]);
Essa função realiza o check out do cliente, mudando o status da reserva de 1 para 0 caso o quarto
Esteja ocupado, efetivamente deixando o quarto livre novamente.

```c
void visualizarReservas(Reserva hotel[NUM_ANDARES][NUM_QUARTOS_POR_ANDAR], int totalReservas);
Essa função lista todos os quartos disponíveis, mostrando quais quartos ainda estão livres, quais estão
Ocupados ou Bloqueados, e mostrando ao usuário através de uma lista que lê a matriz.

```c
void bloquearQuarto(Reserva hotel[NUM_ANDARES][NUM_QUARTOS_POR_ANDAR]);
Essa função permite bloquear um quarto, tornando-o indisponível para aluguer por algum tempo
Ela utiliza um ponteiro que muda o valor do quarto digitado de 1 para 2.
Eu implementei essa função pensando que uma faxina muito pesada ou investigação policial estariam ocorrendo no quarto

```c
void desbloquearQuarto(Reserva hotel[NUM_ANDARES][NUM_QUARTOS_POR_ANDAR]);
Essa função desbloqueia um quarto, tornando-o disponível novamente para aluguel.
É a única maneira de tornar um quarto bloqueado utilizável novamente.
