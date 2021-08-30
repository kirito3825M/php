# php 
nombre : Cargar paquete de Python

en :
  liberación :
    tipos : [creado]

trabajos :
  desplegar :
    se ejecuta : ubuntu-latest
    pasos :
    - usos : acciones / pago @ v1
    - nombre : configurar Python
      usos : acciones / setup-python @ v1
      con :
        Python-versión : ' 3.x '
    - nombre : Instalar dependencias
      ejecutar : |
        python -m pip install - actualizar pip
        pip instalar setuptools hilo de rueda
    - nombre : compilar y publicar
      env :
        TWINE_USERNAME : $ {{secretos.PYPI_USERNAME}}
        TWINE_PASSWORD : $ {{secretos.PYPI_PASSWORD}}
      ejecutar : |
        python setup.py sdist bdist_wheel
        dist / * de carga de hilo
