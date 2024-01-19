| Comando                                           | Descripción                                                                                     |
| ------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `docker run [opciones] <imagen> [comando] [args]` | Ejecuta un contenedor a partir de una imagen.                                                   |
| `docker start <nombre_container>`                 | Inicia un contenedor detenido.                                                                  |
| `docker attach <nombre_container>`                | Conecta la entrada y salida estándar a un contenedor en ejecución.                              |
| `docker ps -a`                                    | Muestra una lista de todos los contenedores, incluyendo los detenidos.                          |
| `docker exec -it <nombre_container> bash`         | Ejecuta un comando dentro de un contenedor en ejecución y proporciona una terminal interactiva. |
| `docker commit <nombre_container> <imagen>:<tag>` | Crea una nueva imagen a partir de los cambios realizados en un contenedor.                      |
| `docker images`                                   | Muestra la lista de imágenes disponibles en el sistema.                                         |
| `docker rm <nombre_container>`                    | Elimina uno o más contenedores.                                                                 |
