# @Transactional

### IMPORTANTE

* transação só é suportado em tabelas que possuem o InnoDB como _engine_.

* Como saber se minha tabela tem isso?
  * 1º Abra o MySQL Workbench
  * 2º Selecione o schema que você quer verificar
  * 3º Escreva o seguinte comando na query: ```show table status```
  * 4º Ache a coluna Engine (2ª coluna)
  * 5º Verifique se é igual à ```InnoDB```

---

### Para que serve?

* Indica para o Spring que enquanto o método não for finalizado, ele não dará commit na transição.

---

### Como usar?

* Basta colocar @Transactional no método
* Exemplo
  ```java
  @Transactional
  // Método que pode lançar uma exceção em tempo de execução
  ```

---

### OBS

* Por padrão, o @Transactional não não dá rollback em exceções checadas.
* Como resolver isso?
  * Basta colocar uma propriedade chamada _rollbackFor_.
  * Exemplo
    ```java
    @Transactional(rollbackFor = Exception.class)
    // Método que pode lançar um exceção checada
    ```
    
---

### O que ganho com isso?

* Mais segurança nas operações com o banco de dados

---

### Exemplos em projetos

* [devdojo-courses](https://github.com/ImGabreuw/devdojo-courses/blob/master/spring-boot-2-essentials/trasacao/src/main/java/me/gabreuw/trasacao/service/AnimeService.java)
  ```java
  @Transactional
  public Anime save(AnimePostRequestBody animePostRequestBody) {
      return animeRepository.save(
              AnimeMapper.INSTANCE.toAnime(animePostRequestBody)
      );
  }
  ```
