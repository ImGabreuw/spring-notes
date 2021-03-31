# @RequestParam

### Quando usar?

* Requisição com múltiplos argumentos
* Solução para recursos com o mesmo caminho

### Sintaxe

* Por padrão, o nome no parâmetro é igual ao nome da variável passada no argumento do método.

* Exemplo nas versão + antigas
  ```java
  @GetMapping(path = "/find")
  public ResponseEntity<List<Anime>> findByName(
          @RequestParam(name = "name") String name
  ) {
      return ResponseEntity
              .ok()
              .body(animeService.findByName(name));
  }
  ```
  
* Exemplo nas versão + novas
  ```java
  @GetMapping(path = "/find")
  public ResponseEntity<List<Anime>> findByName(
          @RequestParam String name // Nome do parâmetro = name
  ) {
      return ResponseEntity
              .ok()
              .body(animeService.findByName(name));
  }
  ```
