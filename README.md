# 📚 Sistema de Gerenciamento de Biblioteca Java

![Status do Projeto](https://img.shields.io/badge/status-concluido-success?style=for-the-badge)
![Linguagem](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)

Este é um projeto console em Java desenvolvido para gerenciar as operações principais de uma biblioteca. Ele permite o cadastro, listagem, empréstimo, devolução e exclusão de livros de forma interativa através de um menu no terminal.

O projeto foi construído focando nos conceitos de Orientação a Objetos (POO) em Java, como Encapsulamento, Construtores, Métodos e Manipulação de Coleções (`ArrayList`).

---

## 🛠️ Funcionalidades

O sistema oferece um menu interativo com as seguintes opções:

1.  **✅ Cadastrar Livro:** Permite adicionar um novo livro ao acervo. O ID é gerado automaticamente sequencialmente. O usuário insere Título, Autor e Ano. Todos os livros novos são cadastrados com disponibilidade 'true' (disponível).
2.  **📋 Listar Livros:** Exibe todos os livros cadastrados na biblioteca, utilizando a formatação definida no método `toString()` da classe `Livro`. Mostra ID, Título, Autor, Ano e se o livro está disponível ou não.
3.  **📖 Emprestar Livro:** Permite realizar o empréstimo de um livro através do seu ID.
    * Verifica se o ID existe.
    * Verifica se o livro já está emprestado.
    * Se estiver disponível, altera o status para 'false' (indisponível) e confirma a operação.
4.  **↩️ Devolver Livro:** Permite a devolução de um livro através do seu ID.
    * Verifica se o ID existe.
    * Verifica se o livro realmente estava emprestado.
    * Altera o status de volta para 'true' (disponível) e confirma a operação.
5.  **🗑️ Excluir Livro:** Permite remover permanentemente um livro do acervo através do seu ID.
6.  **🚪 Encerrar Programa:** Finaliza a execução do sistema.

---

## 📂 Estrutura do Código

O projeto é dividido em três classes principais no pacote padrão:

* **`Biblioteca.java`**: A classe principal que contém o método `main`. Ela inicializa o `Scanner` para entrada de dados, o `ArrayList` que serve como banco de dados em memória e contém o loop `do-while` que gerencia o menu e as chamadas para as outras classes.
* **`Livro.java`**: A classe modelo (POJO) que representa a entidade Livro. Possui atributos privados (`id`, `titulo`, `autor`, `ano`, `disponibilidade`), construtor para inicialização, métodos *getters* e *setters* encapsulados e uma sobrescrita do método `toString()` para formatação da exibição.
* **`Servicos.java`**: A classe que contém a lógica de negócios e as operações do sistema. Ela gerencia o `ArrayList<Livro>`.
    * **Atributos:** Possui seu próprio `Scanner`.
    * **Métodos Principais:**
        * `opcao()`: Exibe o menu e lê a escolha do usuário.
        * `adicionarLivro(int id)`: Coleta dados e instancia um novo `Livro`.
        * `listarLivros(ArrayList<Livro> livros)`: Percorre e imprime a lista.
        * `emprestarLivro(ArrayList<Livro> livros, int id)`: Lógica de empréstimo.
        * `devolverLivro(ArrayList<Livro> livros, int id)`: Lógica de devolução.
        * `excluirLivro(ArrayList<Livro> livros, int id)`: Lógica de remoção.

---

## 💻 Tecnologias e Linguagens

* **Linguagem:** Java (versão LTS recomendada, ex: Java 17 ou 21).

---

## 📚 Bibliotecas e Frameworks

* Este é um projeto "Java Puro" (*Plain Old Java Object*), sem frameworks externos.
* **Bibliotecas Utilizadas (Nativas do Java):**
    * `java.util.Scanner`: Para leitura de entrada do usuário no console.
    * `java.util.ArrayList`: Para armazenamento dinâmico dos livros em memória.

---

## 🚀 Pré-requisitos e Instalação

### Pré-requisitos
* Ter o Java Development Kit (JDK) instalado na sua máquina.

### Instalação
1.  Clone o repositório para o seu computador:
    ```bash
    git clone [https://github.com/SEU_USUARIO/sistema-biblioteca-java.git](https://github.com/SEU_USUARIO/sistema-biblioteca-java.git)
    ```
2.  Navegue até o diretório do projeto:
    ```bash
    cd sistema-biblioteca-java
    ```

---

## 🛠️ Instruções de Uso

Você pode rodar este projeto diretamente no terminal ou em uma IDE (como IntelliJ IDEA, VS Code com extensões Java, ou Eclipse).

### Via Terminal
1.  Compile as classes Java:
    ```bash
    javac Biblioteca.java Livro.java Servicos.java
    ```
2.  Execute a classe principal:
    ```bash
    java Biblioteca
    ```

### Como Usar
Ao iniciar, o terminal exibirá um menu. Digite o número da opção desejada e siga as instruções na tela para cadastrar, listar, emprestar, devolver ou excluir livros.

---

## 🛡️ Testes de Software

O projeto passou por testes manuais de funcionamento e depuração para garantir a corretude da lógica:

* **Validação de Empréstimo:** Testado se o sistema impede o empréstimo de um livro que já está emprestado.
* **Validação de Devolução:** Testado se o sistema impede a devolução de um livro que já está disponível.
* **IDs Inexistentes:** Testado se o sistema exibe mensagens de erro corretas ao tentar interagir com um ID de livro que não existe no acervo.
* **Estabilidade do Menu:** Testado o fluxo contínuo do menu (`do-while`) até que a opção de saída seja escolhida.

---

## 📖 Documentação

* Este projeto serve como exemplo prático da utilização de `ArrayList` para manipulação de coleções de objetos em Java.
* Consulte a [Documentação Oficial do Java (Oracle)](https://docs.oracle.com/en/java/javase/index.html) para detalhes sobre as classes `java.util.Scanner` e `java.util.ArrayList`.

---

## 📄 Licença

Este projeto é disponibilizado sob a **Licença MIT**. Sinta-se à vontade para usar, clonar e modificar para fins educacionais ou de estudo.

---

## 🤝 Contribuição

Contribuições são bem-vindas! Se você tiver ideias para melhorar o código, adicionar novas funcionalidades ou corrigir bugs, siga estas etapas:

1.  Faça um **Fork** do projeto.
2.  Crie uma nova **Branch** para sua funcionalidade: `git checkout -b feature/minha-melhoria`.
3.  Faça suas alterações e crie commits semânticos: `git commit -m 'feat: Adiciona filtro de busca de livros'`.
4.  Envie para sua branch: `git push origin feature/minha-melhoria`.
5.  Abra um **Pull Request**.

### Sugestões de melhorias futuras:
* [ ] Persistência de dados (salvar os livros em um arquivo de texto ou JSON para não perder ao fechar o programa).
* [ ] Busca de livros por título ou autor.
* [ ] Interface gráfica simples (Swing ou JavaFX).

---

## ♾️ Gitflow

Para o desenvolvimento deste projeto, adotamos um fluxo de trabalho simplificado:

* **Main Branch:** Contém o código estável e finalizado.
* **Branches de Funcionalidade:** Usadas para desenvolver novas partes do código (`feature/cadastro-livros`, `feature/emprestimo-devolucao`, etc.).

### Commits Semânticos
Procuramos utilizar a convenção de commits semânticos para clareza:
* `feat`: Nova funcionalidade.
* `fix`: Correção de bug.
* `docs`: Alterações na documentação (`README.md`).
* `refactor`: Refatoração de código que não muda o comportamento.

---

## 👥 Contribuidores

* **Kauã Orcia** - Desenvolvedor principal e responsável pelo código.

