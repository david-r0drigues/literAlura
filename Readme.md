# Catálogo de Livros - Projeto Spring Boot

## Descrição

Este projeto é um catálogo de livros desenvolvido em Java usando Spring Boot. O aplicativo permite interagir com usuários via console e busca livros através da API Gutendex. Ele inclui a configuração do ambiente, consumo de API, análise de resposta JSON, inserção e consulta no banco de dados PostgreSQL, e exibição de resultados aos usuários.

## Funcionalidades

- Busca de livros por título através da API Gutendex
- Listagem de livros registrados no banco de dados
- Listagem de autores registrados
- Listagem de autores vivos em um determinado ano
- Listagem de livros por idioma

## Pré-requisitos

- Java 11 ou superior
- Maven ou Gradle
- PostgreSQL
- pgAdmin 4

## Configuração do Ambiente

1. Clone o repositório:
   ```sh
   git clone https://github.com/seu-usuario/seu-repositorio.git

    Navegue até o diretório do projeto:

    sh

cd seu-repositorio

Configure as variáveis de ambiente no arquivo application.properties ou application.yml:

properties

spring.datasource.url=jdbc:postgresql://${DB_HOST}/bookstore_db
spring.datasource.username=${DB_USER}
spring.datasource.password=${DB_PASSWORD}
spring.datasource.driver-class-name=org.postgresql.Driver
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect

Compile e execute o projeto:

sh

./mvnw spring-boot:run

ou

sh

    ./gradlew bootRun

Estrutura do Projeto

    src/main/java/br/com/alura/literalura: Contém os arquivos de código fonte
        model: Contém as entidades JPA (Autor, Livro, DadosLivros, LivroResultadosApi)
        repository: Contém as interfaces de repositório para acesso ao banco de dados (AutorRepository, LivroRepository)
        service: Contém os serviços (ConsumoApi, ConverteDados)
        principal: Contém a classe principal (Principal) que interage com o usuário via console

    src/main/resources: Contém os arquivos de configuração
        application.properties ou application.yml: Arquivos de configuração do Spring Boot

    pom.xml ou build.gradle: Arquivos de configuração de dependências do Maven ou Gradle

Consumo da API Gutendex

O projeto consome dados da API Gutendex para buscar livros por título. A lógica para a chamada da API e processamento da resposta JSON está implementada na classe ConsumoApi.

Exemplo de uso:



public class ConsumoApi {
public String obterDados(String url) {
// Implementação da chamada à API
}
}

Banco de Dados

O projeto utiliza PostgreSQL como banco de dados. As configurações de conexão estão no arquivo application.properties ou application.yml. O mapeamento das entidades está na pasta model.

Exemplo de uma entidade JPA:


@Entity
public class Livro {
@Id
@GeneratedValue(strategy = GenerationType.IDENTITY)
private Long id;

    private String titulo;
    private String autor;
    private String idioma;
    // Outros campos e getters/setters
}

Executando o Projeto

Após configurar o ambiente e compilar o projeto, você pode executar o aplicativo com o seguinte comando:


./mvnw spring-boot:run

ou


./gradlew bootRun

Para interagir com o console, siga as instruções apresentadas no terminal.
Contribuição

Contribuições são bem-vindas! Por favor, abra um pull request ou issue no GitHub.

    Fork o projeto
    Crie uma branch para sua feature (git checkout -b feature/AmazingFeature)
    Commite suas mudanças (git commit -m 'Add some AmazingFeature')
    Push para a branch (git push origin feature/AmazingFeature)
    Abra um Pull Request

Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo LICENSE para mais detalhes.



