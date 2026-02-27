# Tema 1: Introducción a los Sistemas Gestores de Bases de Datos (SGBD) 🗄️

## 1.1 ¿Qué es un SGBD?
Un **SGBD** consiste en una colección de datos interrelacionados y un conjunto de programas para acceder a ellos. 

### Objetivos principales:
* **Almacenamiento y recuperación**: Proporcionar una forma de gestionar la información que sea tanto **práctica** como **eficiente**.
* **Gestión de grandes volúmenes**: Están diseñados para manejar cantidades masivas de datos.
* **Seguridad y fiabilidad**: Deben garantizar que los datos estén protegidos contra accesos no autorizados y fallos del sistema.
* **Integridad**: Evitar resultados anómalos cuando los datos son compartidos por diferentes usuarios.

## 1.1 Aplicaciones representativas
Las bases de datos son el motor de la industria actual:
* **Banca y Finanzas**: Información de clientes, cuentas, préstamos y transacciones en tiempo real.
* **Líneas aéreas**: Reservas y horarios (fueron de las primeras en usar bases de datos distribuidas).
* **Telecomunicaciones**: Registros de llamadas y facturación mensual.
* **Ventas y Comercio**: Gestión de productos, compras e inventarios.
* **Producción**: Gestión de la cadena de proveedores, seguimiento de artículos en factorías e inventarios.
* **Recursos Humanos**: Gestión de empleados, salarios, impuestos y generación de nóminas.

## 1.2 Propósito de los sistemas de bases de datos
Los sistemas de bases de datos surgieron en respuesta a los primeros métodos de gestión informatizada de los datos comerciales. A modo de ejemplo de dichos métodos, típicos de los años sesenta, considérese parte de una entidad bancaria que, entre otros datos, guarda información sobre todos los clientes y todas las cuentas de ahorro. Una manera de guardar la información en la computadora es almacenarla en archivos del sistema operativo. Para permitir que los usuarios manipulen la información, el sistema tiene varios programas de aplicación que gestionan los archivos, incluyendo programas para:
* Efectuar cargos o abonos en las cuentas.
* Añadir cuentas nuevas.
* Calcular el saldo de las cuentas.
* Generar los extractos mensuales.

Estos programas de aplicación los han escrito programadores de sistemas en respuesta a las necesidades del banco. Se añaden nuevos programas de aplicación al sistema según surgen las necesidades. Por ejemplo, supóngase que una caja de ahorros decide ofrecer cuentas corrientes. En consecuencia, se crean nuevos archivos permanentes que contienen información acerca de todas las cuentas corrientes abiertas en el banco y puede que haya que escribir nuevos programas de aplicación para afrontar situaciones que no se dan en las cuentas de ahorro, como los descubiertos. Así, con el paso del tiempo, se añaden más archivos y programas de aplicación al sistema.

Los sistemas operativos convencionales soportan este sistema de procesamiento de archivos típico. El sistema almacena los registros permanentes en varios archivos y necesita diferentes programas de aplicación para extraer y añadir a los archivos correspondientes. Antes de la aparición de los sistemas gestores de bases de datos (SGBDs), las organizaciones normalmente almacenaban la información en sistemas de este tipo.

Guardar la información de la organización en un sistema de procesamiento de archivos tiene una serie de inconvenientes importantes:

* **Redundancia e inconsistencia de los datos.** Debido a que los archivos y programas de aplicación los crean diferentes programadores en el transcurso de un largo período de tiempo, es probable que los diversos archivos tengan estructuras diferentes y que los programas estén escritos en varios lenguajes de programación diferentes. Además, puede que la información esté duplicada en varios lugares (archivos). Esta redundancia conduce a costes de almacenamiento y de acceso más elevados. Además, puede dar lugar a la inconsistencia de los datos; es decir, puede que las diferentes copias de los mismos datos no coincidan.
* **Dificultad en el acceso a los datos.** Los entornos de procesamiento de archivos convencionales no permiten recuperar los datos necesarios de una forma práctica y eficiente. Hacen falta sistemas de recuperación de datos más adecuados para el uso general.
* **Aislamiento de datos.** Como los datos están dispersos en varios archivos, y los archivos pueden estar en diferentes formatos, es difícil escribir nuevos programas de aplicación para recuperar los datos correspondientes.
* **Problemas de integridad.** Los valores de los datos almacenados en la base de datos deben satisfacer ciertos tipos de restricciones de consistencia. Los desarrolladores hacen cumplir esas restricciones en el sistema añadiendo el código correspondiente en los diversos programas de aplicación. Sin embargo, cuando se añaden nuevas restricciones, es difícil cambiar los programas para hacer que se cumplan.
* **Problemas de atomicidad.** Es crucial asegurar que, si se produce algún fallo, los datos se restauren al estado consistente que existía antes del fallo. La transferencia de fondos debe ser atómica—debe ocurrir en su totalidad o no ocurrir en absoluto. Resulta difícil asegurar la atomicidad en los sistemas convencionales de procesamiento de archivos.
* **Anomalías en el acceso concurrente.** Para aumentar el rendimiento global del sistema, muchos sistemas permiten que varios usuarios actualicen los datos simultáneamente. En tales entornos es posible la interacción de actualizaciones concurrentes y puede dar lugar a datos inconsistentes.
* **Problemas de seguridad.** No todos los usuarios de un sistema de bases de datos deben poder acceder a todos los datos. Como los programas de aplicación se añaden al sistema de procesamiento de datos de una forma ad hoc, es difícil hacer cumplir tales restricciones de seguridad.

Estas dificultades, entre otras, motivaron el desarrollo de los sistemas de bases de datos.
> **Dato Clave**: El SGBD centraliza estas tareas, evitando que cada programa tenga que gestionar sus propios archivos, lo que previene la redundancia y la inconsistencia de los datos.


## 1.3 Visión de los datos
Un sistema de bases de datos es una colección de datos interrelacionados y un conjunto de programas que permiten a los usuarios tener acceso a esos datos y modificarlos. Una de las principales finalidades de los sistemas de bases de datos es ofrecer a los usuarios una visión abstracta de los datos. Es decir, el sistema oculta ciertos detalles del modo en que se almacenan y mantienen los datos.

### 1.3.1 Abstracción de datos
Para que el sistema sea útil debe recuperar los datos eficientemente. La necesidad de eficiencia ha llevado a los diseñadores a usar estructuras de datos complejas para la representación de los datos en la base de datos. Dado que muchos de los usuarios de sistemas de bases de datos no tienen formación en informática, los desarrolladores ocultan esa complejidad a los usuarios mediante varios niveles de abstracción para simplificar la interacción de los usuarios con el sistema:

* **Nivel físico.** El nivel más bajo de abstracción describe cómo se almacenan realmente los datos. El nivel físico describe en detalle las estructuras de datos complejas de bajo nivel.
* **Nivel lógico.** El nivel inmediatamente superior de abstracción describe qué datos se almacenan en la base de datos y qué relaciones existen entre esos datos. El nivel lógico, por tanto, describe toda la base de datos en términos de un número pequeño de estructuras relativamente simples. Aunque la implementación de esas estructuras simples en el nivel lógico puede involucrar estructuras complejas del nivel físico, los usuarios del nivel lógico no necesitan preocuparse de esta complejidad. Los administradores de bases de datos, que deben decidir la información que se guarda en la base de datos, usan el nivel de abstracción lógico.
* **Nivel de vistas.** El nivel más elevado de abstracción sólo describe parte de la base de datos. Muchos usuarios del sistema de bases de datos no necesitan toda esta información; en su lugar sólo necesitan tener acceso a una parte de la base de datos. El nivel de abstracción de vistas existe para simplificar su interacción con el sistema.

### 1.3.2 Instancias (ejemplares) y esquemas
Las bases de datos van cambiando a lo largo del tiempo conforme la información se inserta y se elimina.  
La colección de información almacenada en la base de datos en un momento dado se denomina **instancia** de la base de datos.  
El diseño general de la base de datos se denomina **esquema** de la base de datos. Los esquemas se modifican rara vez, si es que se modifican.

Los sistemas de bases de datos tienen varios esquemas divididos según los niveles de abstracción:
* **Esquema físico:** describe el diseño de la base de datos en el nivel físico.
* **Esquema lógico:** describe su diseño en el nivel lógico. Es el más importante para los programadores de aplicación.
* **Subesquemas:** describen diferentes vistas de la base de datos.

Se dice que los programas de aplicación muestran **independencia física respecto de los datos** si no dependen del esquema físico y, por tanto, no hace falta volver a escribirlos si

> **🎙️ Dice el profesor:** "A veces caen"

## 1.4 Lenguajes de bases de datos
Los sistemas de bases de datos proporcionan un lenguaje de definición de datos para especificar el esquema de la base de datos y un lenguaje de manipulación de datos para expresar las consultas y las modificaciones de la base de datos. En la práctica, los lenguajes de definición y manipulación de datos no son dos lenguajes diferentes; en cambio, simplemente forman parte de un único lenguaje de bases de datos, como puede ser el muy usado SQL.

### 1.4.1 Lenguaje de manipulación de datos
Un lenguaje de manipulación de datos (LMD) es un lenguaje que permite a los usuarios tener acceso a los datos organizados mediante el modelo de datos correspondiente o manipularlos. Los tipos de acceso son:
* La recuperación de la información almacenada en la base de datos.
* La inserción de información nueva en la base de datos.
* El borrado de la información de la base de datos.
* La modificación de la información almacenada en la base de datos.

Hay fundamentalmente dos tipos:
* **Los LMDs procedimentales** necesitan que el usuario especifique qué datos se necesitan y cómo obtener esos datos.
* **Los LMDs declarativos** (también conocidos como LMDs no procedimentales) necesitan que el usuario especifique qué datos se necesitan sin que haga falta que especifique cómo obtener esos datos.

Los LMDs declarativos suelen resultar más fáciles de aprender y de usar que los procedimentales. Sin embargo, como el usuario no tiene que especificar cómo conseguir los datos, el sistema de bases de datos tiene que determinar un medio eficiente de acceso a los datos.

Una consulta es una instrucción que solicita que se recupere información. La parte de los LMDs implicada en la recuperación de información se denomina lenguaje de consultas.


### 1.4.2 Lenguaje de definición de datos
Los esquemas de las bases de datos se especifican mediante un conjunto de definiciones expresadas mediante un lenguaje especial denominado lenguaje de definición de datos (LDD). El LDD también se usa para especificar más propiedades de los datos.



Los valores de los datos almacenados en la base de datos deben satisfacer ciertas restricciones de consistencia. El LDD proporciona facilidades para especificar tales restricciones:
* **Restricciones de dominio.** Se debe asociar un dominio de valores posibles a cada atributo (por ejemplo, tipos enteros, tipos de carácter, tipos fecha/hora).
* **Integridad referencial.** Hay casos en los que se desea asegurar que un valor que aparece en una relación para un conjunto de atributos dado aparece también para un determinado conjunto de atributos en otra relación.
* **Asertos.** Un aserto es cualquier condición que la base de datos debe satisfacer siempre.
* **Autorización.** Diferenciación entre los usuarios en cuanto al tipo de acceso que se les permite (lectura, inserción, actualización, eliminación).

El LDD obtiene como entrada algunas instrucciones y genera una salida. La salida del LDD se coloca en el **diccionario de datos**, que contiene metadatos—es decir, datos sobre datos. El sistema de bases de datos consulta el diccionario de datos antes de leer o modificar los datos reales.
## 1.5 Bases de datos relacionales
Las bases de datos relacionales se basan en el modelo relacional y usan un conjunto de tablas para representar tanto los datos como las relaciones entre ellos. También incluyen un LMD y un LDD. La mayor parte de los sistemas de bases de datos relacionales comerciales emplean el lenguaje SQL.

### 1.5.1 Tablas
Cada tabla tiene varias columnas, y cada columna tiene un nombre único. 
El modelo relacional es un ejemplo de **modelo basado en registros**. La base de datos se estructura en registros de formato fijo de varios tipos. Cada tabla contiene registros de un tipo dado y cada tipo de registro define un número fijo de campos, o atributos. Las columnas de la tabla se corresponden con los atributos del tipo de registro.

El modelo relacional oculta los detalles de implementación de bajo nivel (como el uso de comas o nuevas líneas en archivos físicos) a los desarrolladores y usuarios. Es el modelo de datos más ampliamente usado en la actualidad.

> **Nota sobre el diseño:** En el modelo relacional es posible crear esquemas con información duplicada innecesariamente (redundancia). El estudio de cómo distinguir los buenos diseños de esquema de los malos se trata en el Capítulo 7 (Normalización).

### 1.5.2 Lenguaje de manipulación de datos
El lenguaje de consultas de SQL no es procedimental (es declarativo). Usa como entrada varias tablas y devuelve siempre una sola tabla. 

**Ejemplo de consulta SQL (Selección simple):**
```sql
select cliente.nombre_cliente
from cliente
where cliente.ciudad_cliente = 'Peguerinos'
```
## 1.6 Diseño de bases de datos
Los sistemas de bases de datos se diseñan para gestionar grandes cantidades de información. Esas grandes cantidades de información no existen aisladas. Forman parte del funcionamiento de alguna empresa, cuyo producto final puede que sea la información obtenida de la base de datos o algún dispositivo o servicio para el que la base de datos sólo desempeña un papel secundario.

El diseño de bases de datos implica principalmente el diseño del esquema de las bases de datos. En el Capítulo 8 se estudia el proceso general de diseño de las aplicaciones.

### 1.6.1 Proceso de diseño
La fase inicial del diseño de las bases de datos es caracterizar completamente los requisitos de datos de los hipotéticos usuarios. El resultado de esta fase es la **especificación de los requisitos de los usuarios**.

A continuación, el diseñador elige un modelo de datos y traduce esos requisitos en un **esquema conceptual** de la base de datos. En términos del modelo relacional, esto implica decidir qué atributos capturar y cómo agruparlos en tablas. Existen dos vías principales:
1. Usar el **modelo entidad-relación** (Apartado 1.6.3).
2. Emplear algoritmos de **normalización** (Apartado 1.6.4).

El proceso continúa con:
* **Diseño lógico:** Se relaciona el esquema conceptual con el modelo de implementación del sistema que se va a usar.
* **Diseño físico:** Se especifican las características físicas (organización de archivos y estructuras de almacenamiento).

### 1.6.2 Diseño de la base de datos para una entidad bancaria
Para ilustrar el proceso, se consideran las siguientes características de una entidad bancaria:
* **Sucursales:** Identificadas por un nombre único, ciudad y activos.
* **Clientes:** Identificados por `id_cliente`, nombre, calle y ciudad. Pueden tener cuentas y préstamos.
* **Cuentas:** De ahorro o corrientes. Tienen un `número_cuenta` único, saldo y fecha de último acceso.
* **Préstamos:** Identificados por `número_préstamo`, importe y pagos realizados.
* **Empleados:** Identificados por `id_empleado`, nombre, teléfono, antigüedad y jefe directo.

### 1.6.3 El modelo entidad-relación
El modelo de datos entidad-relación (E-R) se basa en un conjunto de objetos básicos, denominados **entidades**, y de las **relaciones** entre esos objetos. 



La estructura lógica se expresa mediante un diagrama E-R con:
* **Rectángulos:** Conjuntos de entidades.
* **Elipses:** Atributos.
* **Rombos:** Conjuntos de relaciones.
* **Líneas:** Unen los componentes.

### 1.6.4 Normalización
El objetivo es generar esquemas que permitan almacenar información sin redundancias innecesarias. Un mal diseño puede provocar:
* **Repetición de la información:** Malgasta espacio y complica las actualizaciones.
* **Imposibilidad de representar determinada información:** Por ejemplo, no poder guardar un cliente si aún no tiene una cuenta, a menos que se usen **valores nulos**.

Los valores nulos indican que el valor no existe o es desconocido, pero resultan difíciles de tratar y es preferible evitarlos mediante un buen diseño original.

## 1.7 Bases de datos basadas en objetos y semiestructuradas
Los investigadores han desarrollado modelos de datos para tratar dominios donde el modelo relacional tradicional presenta limitaciones.

### 1.7.1 Modelos de datos basados en objetos
Se basan en el paradigma de la programación orientada a objetos (POO). Sus conceptos principales aplicados al modelado de datos incluyen:
* **Herencia e identidad de los objetos.**
* **Encapsulación:** Ocultación de la información mediante métodos que ofrecen una interfaz.
* **Sistemas de tipos elaborados:** Incluyen tipos estructurados y colecciones.

El **modelo relacional orientado a objetos** combina estas características con el modelo relacional tradicional.

### 1.7.2 Modelos de datos semiestructurados
Permiten que elementos del mismo tipo tengan conjuntos de atributos diferentes. El lenguaje **XML (eXtensible Markup Language)** es el representante principal; se usa ampliamente para el intercambio de datos y para representar estructuras anidadas con gran flexibilidad.

---

## 1.8 Almacenamiento de datos y consultas
Un sistema de bases de datos se divide en dos componentes funcionales principales: el gestor de almacenamiento y el procesador de consultas.



### 1.8.1 Gestor de almacenamiento
Es el módulo que proporciona la interfaz entre los datos de bajo nivel (almacenados en disco) y los programas de aplicación o consultas. Sus componentes son:
* **Gestor de autorizaciones e integridad:** Comprueba restricciones y permisos.
* **Gestor de transacciones:** Garantiza un estado consistente a pesar de fallos o ejecuciones concurrentes.
* **Gestor de archivos:** Gestiona el espacio en disco.
* **Gestor de la memoria intermedia (Buffer Manager):** Trae datos del disco a la memoria principal según sea necesario.

Implementa estructuras físicas como **archivos de datos**, el **diccionario de datos** (metadatos) e **índices** para acceso rápido.

### 1.8.2 El procesador de consultas
Sus componentes incluyen:
* **Intérprete del LDD:** Registra definiciones en el diccionario de datos.
* **Compilador del LMD:** Traduce instrucciones a un plan de evaluación y realiza la **optimización de consultas** (elige el plan de menor coste).
* **Motor de evaluación de consultas:** Ejecuta las instrucciones de bajo nivel.

---

## 1.9 Gestión de transacciones
Una **transacción** es una unidad lógica de trabajo que debe cumplir con las propiedades de:
* **Atomicidad:** El requisito de "todo o nada"; la operación se realiza por completo o no se hace.
* **Consistencia:** La ejecución debe preservar la corrección de la base de datos (por ejemplo, la suma de saldos en una transferencia).
* **Durabilidad:** Tras una ejecución correcta, los cambios deben persistir a pesar de fallos del sistema.

Es responsabilidad del sistema de bases de datos realizar la **recuperación de fallos** y el **control de concurrencia** para evitar inconsistencias cuando varios usuarios acceden a los datos simultáneamente.



## 💡 Mis Notas de la UNED
> *Añade aquí conceptos de las videoconferencias o dudas sobre el libro base.*
- 
- 

## 🛠️ Relación con mi Stack (Python & SQL)
Aunque el libro explica la teoría, en la práctica lo aplicaré usando:
* **SQL**: Para definir las estructuras de las tablas (DDL) y manipular los datos (DML).
* **Python**: Usando librerías como `psycopg2` o el ORM de **Django** para interactuar con el SGBD de forma programática.
