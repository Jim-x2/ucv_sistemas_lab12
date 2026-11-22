# Laboratorio 12: Implementación de un Perceptrón Simple

## 1. Descripción del proyecto

Este laboratorio tiene como objetivo implementar desde cero un perceptrón simple utilizando Python, para resolver un problema de aprobación preliminar de créditos bancarios.

El modelo utiliza dos variables de entrada: el ingreso mensual y el historial crediticio del cliente. Mediante un proceso de entrenamiento, aprende a clasificar las solicitudes en dos categorías: crédito aprobado (1) y crédito rechazado (0).

## 2. Objetivos

- Implementar una neurona artificial desde cero.
- Comprender el funcionamiento de los pesos y el bias.
- Aplicar una función de activación.
- Entrenar el modelo mediante el ajuste de pesos.
- Validar los resultados utilizando pytest.
- Automatizar las pruebas mediante GitHub Actions.

## 3. Tecnologías utilizadas

- Python 3.12
- Git
- GitHub
- GitHub Actions
- pytest
- Visual Studio Code

## 4. Estructura del proyecto

```text
ucv_sistemas_lab12/
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── src/
│   ├── __init__.py
│   ├── dataset.py
│   └── perceptron.py
│
├── tests/
│   └── test_perceptron.py
│
├── main.py
├── .gitignore
└── README.md
```

## 5. Funcionamiento del perceptrón

El modelo utiliza dos entradas:

- Ingreso mensual.
- Historial crediticio.

Los resultados se representan mediante valores binarios:

- 1: crédito aprobado.
- 0: crédito rechazado.

El perceptrón utiliza pesos inicializados en cero, un bias inicial de cero y una tasa de aprendizaje de 0.1.

La función de activación determina la salida de la neurona:

- Si el valor calculado es mayor o igual a cero, devuelve 1.
- Si el valor calculado es menor que cero, devuelve 0.

El entrenamiento se realiza durante 20 épocas, actualizando los pesos y el bias según el error obtenido.

## 6. Instalación y ejecución

### Requisitos

Tener Python instalado y Git configurado.

### Instalar pytest

```bash
pip install pytest
```

### Ejecutar el programa

```bash
python main.py
```

### Ejecutar las pruebas

```bash
python -m pytest -v
```

## 7. Pruebas automatizadas

Se implementaron dos pruebas utilizando pytest:

**Prueba 1: Aprobación del crédito**

Comprueba que el modelo clasifique correctamente al cliente con entradas [8, 1].

**Prueba 2: Rechazo del crédito**

Comprueba que el modelo clasifique correctamente al cliente con entradas [1, 0].

Resultado obtenido:

```text
tests/test_perceptron.py::test_prediction PASSED
tests/test_perceptron.py::test_rejection PASSED

2 passed
```

## 8. Integración continua con GitHub Actions

Se configuró un workflow denominado CI para automatizar la ejecución de las pruebas.

El proceso realiza las siguientes actividades:

1. Obtiene el código del repositorio.
2. Configura Python 3.12.
3. Instala pytest.
4. Ejecuta las pruebas automatizadas.
5. Informa si el proceso fue exitoso o presentó errores.

El workflow se ejecuta automáticamente cuando se realizan cambios mediante push o pull request.

## 9. Reto MIT: Problema XOR

El problema XOR demuestra una limitación del perceptrón simple, ya que no puede resolver problemas que no son linealmente separables.

Un perceptrón simple utiliza una frontera de decisión lineal. En cambio, un perceptrón multicapa utiliza capas ocultas y funciones de activación no lineales para resolver problemas más complejos.

Por ello, una red neuronal multicapa puede resolver el problema XOR mediante la combinación de varias neuronas artificiales.

## 10. Conclusión

La implementación permitió comprender el funcionamiento de un perceptrón simple, incluyendo sus pesos, bias, función de activación y proceso de entrenamiento.

Asimismo, se verificó su funcionamiento mediante pruebas automatizadas con pytest y se implementó integración continua utilizando GitHub Actions.

Finalmente, el estudio del problema XOR permitió identificar las limitaciones de un perceptrón simple y comprender las ventajas de utilizar redes neuronales multicapa.