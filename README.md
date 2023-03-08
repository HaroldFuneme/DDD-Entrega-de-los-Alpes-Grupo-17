# DDD-Entrega-de-los-Alpes-Grupo-17
pruebas de concepto (POC) de la arquitectura de solución que el grupo 17  propone para escalar el negocio de Entrega de los Alpes (EDA) por medio del modelo multi-source y proveer servicios a terceros por medio de CSaaS

### Integrantes

- Juan Pablo Feliciano Báez
- Harold Hernando Funeme
- Óscar Fernando Álvarez
 
# Experimento con Modificabilidad
## Flujo de trabajo base:

* Recepción de la orden de compra: Cuando se recibe una nueva orden de compra, el sistema debe almacenar los detalles de la orden, incluyendo la lista de productos solicitados.
* Verificación de inventario: Para cada producto solicitado en la orden de compra, el sistema debe verificar en qué bodega se encuentra el producto. Si el producto no está disponible en ninguna bodega, el sistema debe buscar en los centros de distribución. Así, la búsqueda se realiza en:
* Bodegas: El sistema debe buscar en las bodegas para determinar si el producto solicitado está disponible en la ubicación especificada en la orden de compra. Si el producto está disponible en una bodega, el sistema debe actualizar el registro de inventario de la bodega y continuar con el siguiente producto.
* Centros de distribución: Si el producto no está disponible en ninguna de las bodegas, el sistema debe buscar en los centros de distribución para determinar si el producto solicitado está disponible allí. Si el producto está disponible en un centro de distribución, el sistema debe actualizar el registro de inventario del centro de distribución y continuar con el siguiente producto.
* Generación de orden de despacho: Una vez que el sistema ha verificado el inventario de cada producto en la orden de compra, debe generar una orden de despacho con la información de los productos y su ubicación, ya sea en bodegas o centros de distribución.

## microservicios:
* Microservicio de recepción de orden: Este microservicio se encargaría de recibir la orden del usuario y notificarla cuando identifique que la orden es consistente

    Link: https://github.com/HaroldFuneme/DDD-Entrega-de-los-Alpes-Grupo-17-RecepcionOrden

* Microservicio de verificación de inventario: Este microservicio se encargaría de verificar el inventario de cada producto en la orden de compra, buscando en las bodegas y centros de distribución.

    Link: https://github.com/HaroldFuneme/DDD-Entrega-de-los-Alpes-Grupo-17-VerificacionInventario

* Microservicio de generación de órdenes de despacho: Este microservicio se encargaría de generar una orden de despacho con la información de los productos y su ubicación, ya sea en bodegas o centros de distribución.

    Link: https://github.com/HaroldFuneme/DDD-Entrega-de-los-Alpes-Grupo-17-GeneracionOrdenDespacho

## Las tácticas usadas para mejorar la modificabilidad del sistema son:
* Modularidad: El sistema se divide en diferentes microservicios que se encargan de realizar tareas específicas, como la verificación de inventario o la generación de órdenes de despacho. Esto permite que cada microservicio pueda ser modificado y actualizado de manera independiente sin afectar al resto del sistema.
* Abstracción de la capa de datos por medio de interfaces: El sistema separa la lógica de negocio de la lógica de acceso a los datos, utilizando interfaces para interactuar con las bases de datos. Esto permite que las bases de datos puedan ser modificadas sin afectar la lógica de negocio del sistema.
* Comunicación basada en eventos: el sistema logra ser más flexible y desacoplado, ya que los microservicios no necesitan conocer la ubicación o el estado actual de los demás microservicios. Si un microservicio cambia su implementación o se agrega uno nuevo, los demás microservicios no necesitan cambiar para adaptarse a estos cambios.

## Diagrama del Experimento:

![Experimento](https://github.com/HaroldFuneme/DDD-Entrega-de-los-Alpes-Grupo-17/blob/Modifiability/Modifiability/img/Lab-Modifiability-1.png)


Link: https://app.diagrams.net/#G1beUV5X9plAJ4C_OaOZZLAYY1PRWDPLgJ
