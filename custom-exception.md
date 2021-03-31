# Exceções customizadas

### Para que serve?

* Deixar a API com exceções intuitivas para serem mais fáceis de se manipular no front-end

### OBS: códigos 500

* Significado = erros que ocorreram no servidor (EVITAR)
* Exemplo: tratar exceções de "entidade/objeto não encontrado" com exceções customizadas

### Exemplo de como tratá-los

* 1º Forma
  ```java
  @ResponseStatus(code = HttpStatus.NOT_FOUND)
  public class EntityNotFound extends RuntimeException {
      public EntityNotFound(String message) {
          super(message);
      }
  }
  ```
