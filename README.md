# 42-minishell

Esse projeto reproduz em parte o comportamento de um prompt shell, foi realizado em dupla de cadetes. 
A existência de shells está ligada à própria existência de TI. Antigamente, todos os desenvolvedores concordavam que a comunicação com um computador usando os interruptores 1/0 eram seriamente irritantes. Pela lógica eles tiveram a ideia de criar um software para se comunicar com um computador usando linhas interativas de comandos em uma linguagem um pouco próxima da linguagem humana. Graças ao Minishell, pode-se viajar no tempo e encarar e solucionar os problemas que pessoas enfrentaram quando o Windows não existia.

## Como compilar e executar o projeto

#### 1) Copie este repositório para seu computador

```html
git@github.com:prezadopedro/42-minishell.git
```

#### 2) Instale as bibliotecas necessárias para executar as funções da biblioteca readline

```html
sudo apt-get install libreadline6 libreadline6-dev
```

#### 3) Compile o projeto com Makefile

```html
make
```

#### 4) Inicie o arquivo executável

```html
./minishell
```

Se você deseja executar o programa executável automaticamente com sinalizadores valgrind para verificar se há vazamentos, basta escrever `make leak` e pressionar enter.

## Integrações implementadas

| Integrado | Descrição do comando |
|:------|:------|
| `echo` com `-n` | Exibe uma linha de texto para a saída padrão |
| `cd` | Altera o diretório de trabalho do ambiente de execução do shell atual |
| `pwd` | Imprime o nome de arquivo completo do diretório de trabalho atual |
| `export name[=word]` | Define o atributo de exportação para variáveis |
| `unset` | Desconfigura valores e atributos de variáveis e funções |
| `env` | Define cada nome como valor no ambiente e executa o comando |
| `exit` | Faz com que o shell saia com o status de saída especificado |

## Sobre como implementamos o projeto

 Alguns dos principais arquivos que estão no diretório raiz do projeto:

- `include`: contém todos os cabeçalhos necessários para o projeto
- `libft`: nossa própria biblioteca C com algumas funções auxiliares úteis
- `sources`: diretório que contém toda a implementação do projeto
   - `builtins`: diretório de implementação dos builtins requeridos pelo subject do projeto
   - `execute`: diretório que consiste em funções que executam a entrada do usuário
   - `expander`: diretório com arquivos que implementam expansores de shell, como aspas
   - `parser`: diretório com arquivos e funções que implementam a gramática do minishell 
   - `signals`: arquivo que consiste em funções que manipulam eventos do usuário, como `ctrl-C`, `ctrl-D` e `ctrl-\`
   - `utils`: diretório que implementa tabela hash e linked list para armazenar dados

