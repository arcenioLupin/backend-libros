# backend-libros
Backend desarrolado con Java, Maven, spring, ehcache, mapstruct,mapstruct ,spark, RestTemplate para el consumo de la Api Rest
Para levantar la aplicación:

- Utilizando Eclipse , importar la aplicación como proyecto Maven, tiene 4 módulos y un proyecto pricipal: Ventas Rest, VentasServicios, VentasDaos, Dto y Utilidades.
- Se utilizo JDK 1.8. asegurarse de tenerlo seteado en proyecto
- Compilar con Maven el proyecto principal llamado: sistema_ventas (click derecho, Run As/ Maven Install)
- Desplegar en un tomcat el war generado por VentasRest
- Una vez levantada la aplicación en el puerto 8080, tipear esta url en el navegador: http://localhost:8080/VentasRest/hello
- Si todo va bien deberias ver un texto parecido a este: { "code": "200", "message": "Works!! 17b9aa44-3392-4ddb-9681-e0d9091f4929" }
- Luego probar el estado del  servicio con postman enviando una petición GET: http://localhost:8080/VentasRest/api/v1/libros/estadoDelServicio
- Debería obtener: {
  "code": "200",
  "message": "Funcionando"
}
como respuesta.

- Posteriormente puede consultar el listado de libros con una petición GET en postam: http://localhost:8080/VentasRest/api/v1/libros

PD: Se utilizó RestTemplate para consumir la api rest externa, pero siempre obtuve error 403, el código que hace la petición está comentado en el Proyecto VentasDaos, paquete com.pe.ventas.back.daos.libros.impl , clase LibroDao.java, método  obtenerTodos(), linea 37 a la 43, intenté pasarle headers y también setear el certificado ssl en mi aplicación pero finalmente se logró el consumo, pero igual les estoy enviando la pruaba con todolo que he avanzado.
