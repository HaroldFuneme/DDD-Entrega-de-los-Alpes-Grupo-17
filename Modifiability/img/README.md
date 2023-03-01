# Experimento con Modificabilidad

verificar si la arquitectura hexagonal nos brinda los beneficios de modificabilidad. Para esto, se propone crear dos microservicios que compartan una misma base de datos (por ejemplo, MySQL) e integrar un tercero que utilice otra tecnología de base de datos (como Postgres). La idea es utilizar una topología híbrida, en la que los dos primeros microservicios utilicen una base de datos compartida y el tercero utilice una base de datos independiente. Además, se genera una transacción básica que involucre los tres microservicios y permita ver los eventos o mensajes enviados por cada uno de ellos. A continuación se presenta el esquema para ampliar la idea: 

![Modificabilidad](https://github.com/HaroldFuneme/DDD-Entrega-de-los-Alpes-Grupo-17/blob/Modifiability/Modifiability/img/Lab-Modifiability.png)
