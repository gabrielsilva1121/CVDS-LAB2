# CVDS-LAB2

La herramienta Maven
Cuál es su mayor utilidad
Facilitar la creación y gestión de proyectos de Software, basándose en el concepto de modelo de objeto de proyecto (POM).

Presenta una ventaja y es la conectividad remota a su propio repositorio, permitiendo acceso a utilidades adicionales, que solo son usadas si uno lo desea.

Fases de Maven
compile: Genera los archivos .class, compilando las fuentes .java. No termina este en caso de que en algún .class haya un error.
test: Ejecuta los test automáticos de JUnit existentes, abortando el proceso si alguno de ellos falla.
package: Genera el .jar con los .class compilados.
install: Copia los .jar a un directorio en nuestro ordenador, permitiendo que este se pueda usar en otros proyectos maven en la misma máquina.
deploy: Ubica una copia del .jar a un servidor remoto, permitiendo el acceso a este a cualquier otro proyecto maven que tenga acceso a ese servidor.
