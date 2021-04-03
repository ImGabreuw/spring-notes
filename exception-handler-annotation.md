# @ExceptionHandler

### Para que serve?

* Indica para o Spring que toda vez que uma determinada exceção for lança, o método com essa anotação será invocada para tratá-la.

### Como usar?

* Defina qual exceção será tratada por esse método
  ```java
  @ExceptionHandler(MinhaExcecao.class)
  // Método
  ```
  
* OBS: é boa prática criar uma classe para informar mais detalhes sobre a exceção

* Defina como retorno a classe com mais detalhes: ResponseEntity<MinhaExcecaoDetalhes> (SEMPRE)
  
* Passe como parâmetro a exceção que será trada por ele
  ```java
  @ExceptionHandler(MinhaExcecao.class)
  public ResponseEntity<MinhaExcecaoDetalhes> handleMinhaExcecao(MinhaExcecao exception) {
    // Código
  }
  ```
  
* Instancie a classe MinhaExcecaoDetalhes com: 
  * Construtor
    ```java
    @ExceptionHandler(MinhaExcecao.class)
    public ResponseEntity<MinhaExcecaoDetalhes> handleMinhaExcecao(MinhaExcecao exception) {
      MinhaExcecao exception = new MinhaExcecao(...atributos...);
    }
    ```
  * Builder (Lombok)
    ```java
    @ExceptionHandler(MinhaExcecao.class)
    public ResponseEntity<MinhaExcecaoDetalhes> handleMinhaExcecao(MinhaExcecao exception) {
      MinhaExcecao exception = MinhaExcecao
          .builder()
          ...
          atributos
          ...
          .build()
    }
    ```

* Por fim, retorno o objeto na corpo da resposta
  ```java
    @ExceptionHandler(MinhaExcecao.class)
    public ResponseEntity<MinhaExcecaoDetalhes> handleMinhaExcecao(MinhaExcecao exception) {
      MinhaExcecao exception = new MinhaExcecao(...atributos...);
      
      return ResponseEntity
                .status(CcdigoHttp)
                .body(exception);
    }
    

### O que ganho com isso?

* Mais segurança na API.
* Facilita a vida de quem for usar a API.

### Tutoriais 

* [![](http://img.youtube.com/vi/PzK4ZXa2Tbc/maxresdefault.jpg)](https://www.youtube.com/watch?v=PzK4ZXa2Tbc)
