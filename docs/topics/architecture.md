# Estructura/Arquitectura escogida

---

En cuanto a la estructura del proyecto podemos observar una clara estructura por capas (**_By Layer_**)

```
java
 +-com
    +-demo
        +-idealista
            +-aplication //capa llamada servicios
            |
            +-domain
            |
            +-infrastructure // aqui residen dos capas la de controllers y la de repositories
            +-persistence
                +-api // capa controllers
                +-persistence // capa repositories
```

Este tipo de estructura aunque en este caso de uso es aplicable, no sigue alguno de losprincipios SOLID, lo que hace que su refactorización sea de más dificultad ya que por ejemplo resulta más complejo localizar clases que dependan unas de otras ya que estas alejadas en la jerarquia de carpetas.

Por ejemplo, nos encontramos una clase llamada Constants que es utilizada tanto en AdServiceImpl que esta dentro de la carpeta domain, pero ademas estas constantes se usan en InMemoryPersistence.
