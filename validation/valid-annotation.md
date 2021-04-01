# @Valid

### Para que serve?

* Indicar para o Spring fazer a validação do objeto passado no corpo da requisição

---

### Como usar?

* Basta colocar essa anotação no parâmetro do método
* Exemplo
  ```java
  @PostMapping
  public ResponseEntity<MeuObjeto> save(
          @RequestBody @Valid MeuObjetoDTO dto
  ) {
    // Código
  }
  ```

---

### O que ganho com isso?

* Mais integridade nos dados dos objetos

---

### Exemplos em projetos

* [devdojo-courses](https://github.com/ImGabreuw/devdojo-courses/blob/master/spring-boot-2-essentials/validacao-de-campos/src/main/java/me/gabreuw/validacaodecampos/resource/AnimeResource.java)
  ```java
  @PostMapping
  public ResponseEntity<Anime> save(
          @RequestBody @Valid AnimePostRequestBody animePostRequestBody
  ) {
      return ResponseEntity
              .status(HttpStatus.CREATED)
              .body(animeService.save(animePostRequestBody));
  }
  ```
