# CVDS-LAB2

## Elaborado por 
GABRIEL ALEJANDRO SILVA LOZADA
ANGEL NICOLAS CUERVO NARANJO

# **La herramienta Maven**

### Cuál es su mayor utilidad

Facilitar la creación y gestión de proyectos de Software, basándose en el concepto de modelo de objeto de proyecto (POM).

Presenta una ventaja y es la conectividad remota a su propio repositorio, permitiendo acceso a utilidades adicionales, que solo son usadas si uno lo desea.

### Fases de Maven

 1. **_compile_**: Genera los archivos __.class__, compilando las fuentes __.java__. No termina este en caso de que en algún __.class__ haya un error.
 2. **_test_**: Ejecuta los test automáticos de **JUnit** existentes, abortando el proceso si alguno de ellos falla.
 3. **_package_**: Genera el **.jar** con los **.class** compilados.
 4. **_install_**: Copia los **.jar** a un directorio en nuestro ordenador, permitiendo que este se pueda usar en otros proyectos **maven** en la misma máquina.
 5. **_deploy_**: Ubica una copia del **.jar** a un servidor remoto, permitiendo el acceso a este a cualquier otro proyecto **maven** que tenga acceso a ese servidor.

### Para qué sirven los plugins

> **¿Qué es un plugin?**
> 
> Un Plugin es un fragmento o componente de código hecho para ampliar las funciones de un programa o de una herramienta.

## Cómo se crea un proyecto en Maven con ayuda de arquetipos

Para poder crear un proyecto en maven con arquetipos es necesario:

```
mvn archetype:generate -Dfilter=maven-archetype-quickstart 
```
Esto nos generará un proyecto de manera interactiva, lo que después nos solicitará:

- Grupo
- Id del artefacto
- Versión
- Paquete

![image](https://user-images.githubusercontent.com/98113396/223009501-40854ec4-0949-4c3e-8003-34f6ed809d6b.png)

 escribimos el comando ```tree```,nos mostrara todos los archivos creados por maven:

```
tree
```
similar a como se muestra a continuación 

![image](https://user-images.githubusercontent.com/98113396/223009639-e5f9a258-25c7-4a15-be0d-4fc0e226f76f.png)

# AJUSTAR ALGUNAS CONFIGURACIONES EN EL PROYECTO
Hay que cambiar la version delcompilador de Java a la versión 8, para ello, agregue la sección properties antes de la sección de dependencias:\
\<properties>\
<maven.compiler.target>1.8</maven.compiler.target>\
<maven.compiler.source>1.8</maven.compiler.source>\
\</properties>

![image](https://user-images.githubusercontent.com/98113396/223011034-7c5d2850-aea6-47de-a8f8-5d3869ac9b99.png)


## Compilando y Ejecutando
Para compilar ejecute el comando:
```
$ mvn package
```
Si maven no actualiza las dependencias utilice la opción -U asi:
```
$ mvn -U package
```
* Busque cuál es el objetivo del parámetro "package" y qué otros parámetros se podrían enviar al comando mvn.
   * El objetivo de package es ***"empaquetar el proyecto"*** por defecto crea un ejecutable ***.jar***


* Busque cómo ejecutar desde línea de comandos, un proyecto maven y verifique la salida cuando se ejecuta con la clase App.java como parámetro en "mainClass"
   * Para ejecutar el proyecto debe ejecutar el siguiente comando:
      ```
      mvn exec:java -Dexec.mainClass="edu.eci.cvds.patterns.App"
      ```

* Buscar cómo enviar parámetros al plugin "exec".
   * Para enviar parametro ingresesar el siguiente comando 
      ```
      mvn exec: exec -Dexec.executable = "maven" [-Dexec.workingdir = "/ tmp"] -Dexec.args = "- X myproject: dist"
      ```
      
* Ejecutar nuevamente la clase desde línea de comandos y verificar la salida: ```Hello World!``` \

![image](https://user-images.githubusercontent.com/98113396/223009831-718b1e83-a1ec-4f89-8896-b074fc78d400.png)
![image](https://user-images.githubusercontent.com/98113396/223009863-7b8200a3-dddc-4be2-8b62-8ce6eddedf14.png)

* Ejecutar la clase desde línea de comandos enviando su nombre como parámetro y verificar la salida. Ej: ```Hello Pepito!``` \

![image](https://user-images.githubusercontent.com/98113396/223009919-3b49910b-ec0c-4cb8-9a92-b5e016d3d58f.png)

* Verifique cómo enviar los parámetros de forma "compuesta" para que el saludo se realice con nombre y apellido. \

![image](https://user-images.githubusercontent.com/98113396/223010273-b7d865b2-0f82-4e73-9a0a-6144a8932a41.png)

## Hacer el esqueleto de la aplicacion
* Finalice el esqueleto de la aplicacion
* Ejecute múltiples veces la clase ShapeMain, usando el plugin exec de maven con los siguientes parámetros y verifique la salida en consola para cada una:
   * ***Sin parámetros:***  \

![image](https://user-images.githubusercontent.com/98113396/223010371-92e7dbcd-8cc2-48fb-9375-cef0aca26c0a.png)
Este no es una entrada valida ya que la clase ```ShapeMain``` requiere un parametro, sin embargo la clase lo maneja y atiende la falta del parametro.
   * ***Parámetro: qwerty***  \

![image](https://user-images.githubusercontent.com/98113396/223010458-2ee20eed-f106-43d7-9a69-f8bd41702f90.png)
Este no es una entrada valida ya que la clase ```ShapeMain``` requiere un parametro de una figura establecida en la clase ```RegularShapeType```, sin embargo la clase atrapa y maneja el error.
   * ***Parámetro: pentagon***  \

![image](https://user-images.githubusercontent.com/98113396/223010539-258bbb8b-98b2-4f5a-96f2-6d554f85f1aa.png)
Este no es una entrada valida ya que la clase ```ShapeMain``` requiere un parametro de una figura establecida en la clase ```RegularShapeType```, sin embargo la clase atrapa y maneja el error. 
   * ***Parámetro Hexagon***  \

![image](https://user-images.githubusercontent.com/98113396/223010589-a6dfa459-17f3-44fe-a406-c9e5cf4705dc.png)
* Investigue para qué sirve ***"gitignore"*** y cómo se usa. Para futuras entregas, debe estar configurado
   * Sirve para decirle a Git qué archivos o directorios completos debe ignorar y no subir al repositorio de código. \







