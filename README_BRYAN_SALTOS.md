# README - Web Scraping con Python

Este notebook fue hecho como parte de la práctica de **web scraping**. La idea principal es aprender a leer el código HTML de una página, identificar las partes que nos interesan y luego extraer información como menús, enlaces y atributos. Para esto se usa principalmente la librería `BeautifulSoup`, que es la que nos facilita navegar dentro del árbol HTML sin tener que hacerlo “a mano”.

Lo que se hizo en el notebook fue ir resolviendo pequeños retos (challenges) donde había que encontrar ciertas etiquetas, acceder a clases y obtener valores como los `href`. Por ejemplo, en uno de los ejercicios había que extraer todos los enlaces del **mainmenu**, y con un simple `soup.select("ul.mainmenu a")` ya se podían obtener. Luego, con un bucle, se sacaban solo los atributos `href`, que son los que contienen las direcciones a donde apunta cada link.

Algo importante en este trabajo fue el tema del **error del sidemenu**. Al inicio, el HTML tenía marcado algo con la clase `sidemenu`, pero esa clase realmente no existía en el documento que estábamos usando. Por eso, cuando intentábamos buscar elementos con ese selector, no devolvía nada. Fue un error que parecía tonto pero en la práctica es común cuando uno hace scraping: si la clase o el id que usas no coincide exactamente con lo que está en el HTML, no vas a conseguir nada. La solución fue cambiar `sidemenu` por `dropdown-item`, que sí era la clase real que tenían los elementos del menú en la página. Después de esa corrección, el código empezó a funcionar y ya se pudieron listar los enlaces como se esperaba.

En general, lo que se ve en este deber es:
- Cómo abrir y analizar un HTML en Python con `BeautifulSoup`.
- Cómo buscar elementos con `find`, `find_all` y `select`.
- Cómo acceder a los atributos de las etiquetas, especialmente los `href`.
- Cómo depurar cuando algo no funciona, revisando que los selectores CSS estén bien escritos.

El notebook no es un proyecto grande, pero sí sirve para afianzar los conceptos básicos de scraping. También deja la enseñanza de que no siempre el error está en el código de Python; a veces el error está en cómo interpretamos el HTML. En este caso, una sola palabra mal puesta (`sidemenu` en lugar de `dropdown-item`) hacía que el ejercicio no funcionara.

En conclusión, este trabajo fue útil para practicar el scraping desde cero, entender mejor cómo funciona `BeautifulSoup` y también para desarrollar la paciencia de revisar bien los selectores cuando algo no sale. Es un buen primer paso para proyectos más grandes donde se quiera recopilar datos de páginas web de manera automática.
