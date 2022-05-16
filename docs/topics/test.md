# Test

---

Aunque para este caso de uso no era imprescindible, realizar más test, con anuncios e imágenes incompletas o esperar fallos, hubiera sido adecuado ya que como se ha visto, si no existen anuncios en la apliación que use esta API, recibirá un error 500 desde el backend.

Por ello hubiera mockeado llamadas a los endpoint en situaciones en las que no hubiera anuncios, o solo hubiera anuncios irrelevantes, etc...

Por ejemplo:

```
@Test
public void givenMockingIsDoneByMockito_whenGetIsCalled_shouldReturnMockedObject() {
    Mockito
        .when(restTemplate.getForEntity(
            “http://localhost:8080/ads/public”, PublicAd.class))
        .thenReturn(new ResponseEntity(ads, HttpStatus.OK));
...
```
