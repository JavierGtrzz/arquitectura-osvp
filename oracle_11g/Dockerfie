# Usamos la imagen base que ya tiene Oracle 11g instalado
FROM wnameless/oracle-xe-11g-r2 AS base

# Definimos las variables de entorno requeridas por tu práctica
# Estas se mantendrán activas cada vez que inicies el contenedor
ENV ORACLE_HOME=/u01/app/oracle/product/11.2.0/xe
ENV ORACLE_SID=XE
ENV PATH=$ORACLE_HOME/bin:$PATH
# ======================
# DEV
# ======================
FROM base AS dev
# Exponemos el puerto estándar de Oracle
EXPOSE 1521