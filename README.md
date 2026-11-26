# Sistema de Gerenciamento de Estoque Tributável

Projeto acadêmico desenvolvido em Java para funcionar no terminal. O sistema controla funcionários, clientes, produtos e movimentações de estoque, além de apresentar uma estimativa didática de tributação.

## Funcionalidades

- cadastro e listagem de funcionários;
- cadastro e listagem de clientes por CPF;
- cadastro de produtos;
- registro de entrada e saída de estoque;
- consulta do estoque completo e dos itens no estoque mínimo;
- relatório do valor armazenado e do tributo estimado;
- escolha do regime tributário;
- validação de CPF, códigos, quantidades, preços e opções do menu;
- persistência local em arquivo de texto.

## Estrutura do repositório

| Caminho | Conteúdo |
| --- | --- |
| `src/Main.java` | Código principal em Java |
| `pseudocodigo/` | Versão do algoritmo em Portugol |
| `docs/DOCUMENTACAO.md` | Contexto, objetivos, regras e explicações |
| `docs/fluxograma/` | Fluxograma em Draw.io e PDF |
| `docs/relatorio/` | Documento acadêmico em Word |
| `docs/apresentacao/` | Apresentação do projeto em PowerPoint |

## Como executar

É necessário ter o JDK 17 ou superior instalado.

```bash
javac -d out src/Main.java
java -cp out Main
```

## Persistencia dos dados

Os cadastros, o estoque e o regime tributário são salvos em `SistemaEstoqueTributavel/estoque.txt`, dentro da pasta pessoal do usuário do computador. No Windows, por exemplo, o caminho é `C:\\Users\\SEU_USUARIO\\SistemaEstoqueTributavel\\estoque.txt`. Cada perfil do sistema operacional tem seus próprios dados; o programa não sincroniza dados entre computadores.

Na primeira abertura desta versão, se existir um `estoque.txt` na pasta de execução e ainda não houver um arquivo na pasta pessoal, o sistema copia os dados antigos para lá sem apagar o original. Se o arquivo for removido, o programa pede o regime novamente e cria um novo. O arquivo `estoque.lock` impede duas instâncias simultâneas; sua presença após fechar o programa é normal. Em sistemas sem substituição atômica, um `estoque.txt.bak` pode guardar a versão anterior.

Arquivos antigos com CPF ou e-mail inválido geram avisos, mas continuam acessíveis. Novos cadastros exigem validação. O TXT contém CPF e e-mail sem criptografia; mantenha a pasta pessoal protegida e não compartilhe o arquivo.

## Regras principais

- o funcionário deve existir antes do cadastro de produto e da entrada;
- o cliente deve ter CPF válido e estar cadastrado antes da venda;
- uma saída não pode ser maior que a quantidade disponível;
- códigos não podem ser repetidos;
- preço, quantidade, estoque mínimo e alíquota passam por validação.

## Tributação

As alíquotas usadas pelo programa têm finalidade acadêmica e servem para demonstrar o cálculo sobre o estoque. Uma aplicação comercial precisaria consultar a legislação e os dados fiscais vigentes.

## Autores

Vinícius Salgado, Vinícius Barbosa e José Elias.
