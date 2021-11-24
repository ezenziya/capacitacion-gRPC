# Ejemplo gRPC

Implimentacion de un gRPC (google Remote Procedure Call)

## Armar un entorno virtual para Python

Altamente recomendado para no tener conflicto entre las librerias...y siempre hay conflicto entre las liberias de Python

```sh
python -m pip install virtualenv
virtualenv venv
source venv/bin/activate 
#si tienen windows es venv\Scripts\activate
```

## Instalando Librerias

Para esta API se utilizan:
- grpcio: como servidor web
- grpcio-tools: como conector con la DB


```sh
python -m pip install --upgrade pip
#Instalar librerias
python -m pip install grpcio
python -m pip install grpcio-tools

# se puede bajar todo el codigo fuente del ejemplo de
# git clone -b v1.41.0 https://github.com/grpc/grpc
# cd grpc/examples/python/helloworld
```

## Para ejecutar el servicio

Y luego ejecutamos el servidor:

```sh
python server.py
```

el cliente se puede ejecutar con:

```sh
python client.py
```

## Modificaciones al servicio

Los archivos helloworld_pb2.py y hellowrld_pb2_grpc.py no se tocan, se ejecutan desde el compilador de grcp. Se utilizan los prototipos de servicio

```sh
python -m grpc_tools.protoc -I./protos --python_out=. --grpc_python_out=. ./protos/helloworld.proto
```