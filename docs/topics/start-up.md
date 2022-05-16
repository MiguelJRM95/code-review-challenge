# Arranque de la API

---

En mi opinión un code review debe incluir, un arranque de la app/API o feature, para ver si la aplicación compila, para ello sería bueno que llevase un pequeño readme o documentación para el arranque de esta API.

En mi caso, que mi entorno estaba ya preparado, la he podido arrancar con:

` mvn spring-boot:run`

Al arrancarla los endpoints:

> /ads/quality
> 
> /ads/public

Daban un error 500.

Para que los dos endpoints previos funcionasen tiene que acceder primero a:

> /ads/score

Y con ello se ejecuta:

```
 @GetMapping("/ads/score")
    public ResponseEntity<Void> calculateScore() {
        adsService.calculateScores();
        ...
}
```

es este **adService.calculateScore** (AdsController#29) el que hace que los otros endpoints tengan anuncios para mostrar y no lancen error 500.

---

Una solución sería llamar a este metodo al arrancar la aplicación, si se quiere que tenga datos en memoria si solo se utiliza para pruebas, code reviews o entrevistas tecnicas, etc...

O simplemente ejecutar el test con los datos de prueba y que estos test contengan pruebas de llamada a los endpoints.
