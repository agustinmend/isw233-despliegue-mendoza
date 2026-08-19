# isw233-despliegue-mendoza
## Uso de IA
-investigar estructura de archivos para flask
-elaboracion de css
-correccion de etiquetas html
## Levantamiento del servicor sin docker
-En primera no corrio sospecho del debuger active que me imprime la consola,
-Ahora funciona en mi maquina pero no el servidor
-Acabo de abrir ambos ssh uno donde corre el flask y el otro donde hace la solicitud con ambos comandos si hubo repuesta, ahora cuando coloco la direccion en el navegador no me carga lo cual supongo que puede ser que ambas maquinas ssh pertenecen a la mismar instancia y por eso es que si funcionan las peticiones, segun creo podria ser algo tipo como que falte habilitar el puerto
-el parametro en flask fue el de host a 0.0.0.0 debido a q si ponemos cualquier otro solo se va a escuchar a esa ip, pero al poner 0.0.0.0 estamos diciendo que escuche a todos

-El ssh en produccion deberia ser restringido solo a direcciones especificas q conocemos dado que si lo ponemos para todos cualquiera puede intentar conectarse y ya para todo publico tendria q haber una unica entrada q sea gestionada por un proxy inverso como ngnix

## Docker
-El COPY en el dockerfile copia los elementos de mi maquina local a el contenedor, en este caso al usar el . esta diciendo q copie todo los elementos que estan en la misma altura del dockerfile y los pegue en una carpeta /site/ dentro del contenedor, si tuviera un .pem en el directorio al no haber nada q me limite yo pienso que igual lo copiaria al contenedor lo cual no seria muy bueno q digamos, en el caso de los puertos a lo q yo tengo entendido el EXPOSE en Dockerfile es mas como documentacion no es que lo exponga por ende se seguiria escuchando en el 8000