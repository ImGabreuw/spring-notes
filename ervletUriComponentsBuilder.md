# ServletUriComponentsBuilder 

### Nome do arquivo na URL

  ```java
  String url = ServletUriComponentsBuilder
                .fromCurrentContextPath() // caminho base da aplicação (http://localhost:8080)
                .path("/download") // caminho até o recurso que gerencia os arquivos na aplicação (http://localhost:8080/download)
                .path(fileName) // adicionar o nome do arquivo no caminho atual (http://localhost:8080/download/arquivo.png)
                .toUriString(); // construção da url
  ```
  
* Exemplo retirado do projeto [spring-boot-multipartfile-sample]()

  ```java
  public static FileDTO of(MultipartFile file) {
      String fileName = file.getName();
      String url = ServletUriComponentsBuilder.fromCurrentContextPath()
              .path("/download")
              .path(fileName)
              .toUriString();

      return new FileDTO(
              fileName,
              file.getContentType(),
              url
      );
  }
  ```
