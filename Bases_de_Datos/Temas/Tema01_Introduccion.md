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

## 1.2 Evolución e Impacto de las Bases de Datos
La forma en que interactuamos con los datos ha cambiado radicalmente en las últimas décadas:

* **Inicios (años 60-80)**: Pocas personas interactuaban directamente con los sistemas; se hacía a través de informes impresos o agentes (cajeros de banco, agentes de viajes).
* **Revolución de Internet (finales de los 90)**: El acceso se volvió directo para el usuario a través de interfaces Web (banca online, reserva de vuelos, matrículas universitarias).
* **Actualidad**: Las interfaces ocultan la complejidad. La mayoría de las personas interactúan con bases de datos constantemente sin ser conscientes de ello.

## 1.3 Propósito de los Sistemas de Bases de Datos
Los SGBD surgieron como solución a los problemas de los antiguos métodos de gestión basados en archivos del sistema operativo.

### El ejemplo bancario:
Antes de los SGBD, una entidad bancaria guardaba la información en archivos manejados por programas de aplicación para:
1. Efectuar cargos o abonos.
2. Añadir cuentas nuevas.
3. Calcular saldos y generar extractos mensuales.

> **Dato Clave**: El SGBD centraliza estas tareas, evitando que cada programa tenga que gestionar sus propios archivos, lo que previene la redundancia y la inconsistencia de los datos.

## 1.4 Aplicaciones extendidas
Además de la banca y telecomunicaciones, son esenciales en:
* **Producción**: Gestión de la cadena de proveedores, seguimiento de artículos en factorías e inventarios.
* **Recursos Humanos**: Gestión de empleados, salarios, impuestos y generación de nóminas.





## 💡 Mis Notas de la UNED
> *Añade aquí conceptos de las videoconferencias o dudas sobre el libro base.*
- 
- 

## 🛠️ Relación con mi Stack (Python & SQL)
Aunque el libro explica la teoría, en la práctica lo aplicaré usando:
* **SQL**: Para definir las estructuras de las tablas (DDL) y manipular los datos (DML).
* **Python**: Usando librerías como `psycopg2` o el ORM de **Django** para interactuar con el SGBD de forma programática.
