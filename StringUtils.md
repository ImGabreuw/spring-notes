# StringUtils do Spring Framework

### Método _cleanPath_

* Reajusta os separadores do Windows, ou seja, substitui "\" por "/"

* Exemplo retirado do projeto spring-boot-multipart-sample

  ```java
  public String storeFile(MultipartFile file) {
      String cleanedFileName = StringUtils.cleanPath(file.getOriginalFilename());
      Path filePath = Paths.get(fileStoragePath + "\\" + cleanedFileName);

      try {
          Files.copy(file.getInputStream(), filePath, StandardCopyOption.REPLACE_EXISTING);
      } catch (IOException e) {
          log.error(e);
          throw new RuntimeException("Ocorreu um erro ao copiar o arquivo para o diretório.", e.getCause());
      }

      return cleanedFileName;
  }
  ```
