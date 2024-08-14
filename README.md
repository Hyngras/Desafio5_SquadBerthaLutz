# 💻 Bootcamp Back-end Python & Django da WoMakersCode 👩‍💻

Repositório para os exercícios do Desafio 5 da Semana 04 do Bootcamp Back-end Python e Django do **Squad Bertha Lutz**.

O desafio consiste em... o que foi feito...


🧩 Explorando o conceito de classe
Os conceitos de classe aparecem em nosso sistema de gerenciamento de biblioteca de maneira fundamental, organizando as informações e funcionalidades em componentes bem definidos e modularizados. Cada classe representa um elemento essencial da biblioteca, facilitando a interação entre autores, usuários, livros e o processo de empréstimo. Veja abaixo a explicação de cada uma dessas classes:

📚 Classe Pessoa - A base abstrata para autoras e usuárias

A classe Pessoa é a fundação abstrata do sistema, encapsulando atributos comuns a todas as pessoas que interagem com a biblioteca. Esta classe é abstrata (ABC), o que significa que ela não pode ser instanciada diretamente, mas serve como uma base para outras classes, como Autor e Usuario.

Atributos:
nome: Nome da pessoa.
telefone: Número de telefone.
email: Endereço de email (opcional).
endereco: Endereço físico (opcional).
Métodos:
exibir_info_completa(): Exibe todas as informações disponíveis sobre a pessoa.
get_info(): Um método abstrato que deve ser implementado pelas subclasses para fornecer detalhes específicos.


✒️ Classe Autor - Representando pessoas criadoras de conteúdo

A classe Autor herda de Pessoa e se especializa em representar os autores dos livros da biblioteca. Além das informações pessoais herdadas, Autor pode listar os livros que escreveu, integrando-se diretamente ao acervo da biblioteca.

Métodos:
get_info(): Retorna uma string com os detalhes do autor.
listar_livros(livros): Gera uma lista dos títulos de livros associados a este autor.


👥 Classe Usuario - Pessoas que usam a biblioteca

A classe Usuario também herda de Pessoa, mas é focada nos leitores que utilizam a biblioteca. Esta classe gerencia os empréstimos feitos pelo usuário, permitindo que eles acessem e controlem suas atividades na biblioteca.

Atributos:
emprestimos: Lista de empréstimos associados ao usuário.
Métodos:
get_info(): Retorna uma string com os detalhes do usuário.
adicionar_emprestimo(emprestimo): Adiciona um novo empréstimo ao histórico do usuário.
listar_emprestimos(): Retorna uma lista de livros emprestados pelo usuário, com as respectivas datas de devolução.


📖 Classe Livro - A essência do acervo

A classe Livro representa os livros disponíveis na biblioteca. Com atributos que vão desde o título até o ISBN, essa classe é a chave para organizar e gerenciar o acervo de maneira eficiente.

Atributos:
titulo: Título do livro.
editora: Nome da editora.
autores: Lista de objetos Autor.
generos: Lista de gêneros literários.
isbn: Número ISBN (opcional).
ano_publicacao: Ano de publicação (opcional).
sinopse: Breve descrição do livro (opcional).
_exemplares: Lista de objetos Exemplar disponíveis.
Métodos:
adicionar_exemplar(exemplar): Adiciona um exemplar do livro ao acervo.
remover_exemplar(): Remove um exemplar do acervo.
exemplares_disponiveis: Retorna o número de exemplares disponíveis para empréstimo.


📚 Classe Exemplar - Gerenciando as cópias físicas

A classe Exemplar representa uma cópia física de um livro. Cada Exemplar tem um estado que indica se ele está disponível para empréstimo ou se está emprestado.

Atributos:
livro: O objeto Livro ao qual o exemplar pertence.
estado: Estado atual do exemplar (disponível ou emprestado).
Métodos:
emprestar(): Marca o exemplar como emprestado.
devolver(): Marca o exemplar como disponível.


🔄 Classe Emprestimo - Orquestrando o ciclo de empréstimos

A classe Emprestimo é a espinha dorsal do sistema de empréstimos, gerenciando todo o ciclo de vida de um empréstimo, desde a retirada do livro até a sua devolução ou renovação.

Atributos:
usuario: O objeto Usuario que fez o empréstimo.
exemplar: O objeto Exemplar que foi emprestado.
data_emprestimo: Data em que o empréstimo foi feito.
data_devolucao_prevista: Data prevista para a devolução.
data_devolucao: Data real de devolução (se já devolvido).
renovacoes: Número de vezes que o empréstimo foi renovado.
max_renovacoes: Número máximo de renovações permitido.
estado: Estado atual do empréstimo (emprestado ou devolvido).
Métodos:
devolver(): Marca o empréstimo como devolvido e atualiza o estado do exemplar.
renovar(): Renova o empréstimo, ajustando a data de devolução prevista.
esta_atrasado(): Verifica se o empréstimo está atrasado.


🌟 Conclusão
Cada classe no nosso sistema foi cuidadosamente projetada para representar aspectos cruciais do gerenciamento de uma biblioteca, desde a gestão dos livros e autores até o controle preciso dos empréstimos e das interações dos usuários. Este design modular e orientado a objetos não só melhora a organização interna do código como também facilita a expansão e manutenção do sistema, oferecendo uma base sólida para futuros desenvolvimentos.


Os conceito de herança aparece em... de maneira...


Os conceito de propriedade aparece em... de maneira...


Usamos o conceito de encapsulamento para privar o atributo `nome` nas classes `Usuario()` e `Autor()`, que herdam da classe `Pessoa()`, dessa forma um novo valor não pode ser adicionado após o objeto ser inicializado, apenas a informação de contato pode ser diretamente alterada. Já o atributo `_exemplares`  da classe `Livro()` está apenas protegido.


Os conceito de classe abstrata aparece em... de maneira...
