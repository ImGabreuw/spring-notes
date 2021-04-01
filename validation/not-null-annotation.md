# @NotNull

### Para que serve?

* Validar um atributo para que não seja nulo
* OBS: por convenção essas validações são feitas nos objetos [DTO](https://pt.stackoverflow.com/questions/31362/o-que-%C3%A9-um-dto)

---

### Propriedades

* message = definir uma messagem quando essa regra for descumprida

### Como usar?

* Basta colocar essa anotação no campo do objeto onde seja necessário a validação
* Exemplo
  ```java
  @NotNull(message = "The name cannot be null")
  private String name;
  ```

---

### O que ganho com isso?

* Mais integridade nos dados dos objetos

---

### Exemplos em projetos

* [devdojo-courses](https://github.com/ImGabreuw/devdojo-courses/blob/master/spring-boot-2-essentials/validacao-de-campos/src/main/java/me/gabreuw/validacaodecampos/request/AnimePostRequestBody.java)
  ```java
  @Getter
  public class AnimePostRequestBody {

    @NotEmpty(message = "The anime name cannot be empty")
    @NotNull(message = "The anime name cannot be null")
    private String name;
    
  }
  ```
