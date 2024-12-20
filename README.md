# smishing-classification

Este proyecto implementa un modelo de detección de smishing (phishing por SMS) utilizando la biblioteca SimpleTransformers. El código está diseñado para ejecutarse en un entorno Python y procesar datos de SMS para tareas de clasificación.

## Características
- Detecta mensajes de smishing utilizando modelos de transformadores preentrenados.
- Configurable para utilizar aceleración por GPU con CUDA.
- Soporta la carga y procesamiento de conjuntos de datos de SMS para clasificación binaria.

## Requisitos

Asegúrate de tener instaladas las siguientes dependencias:

- Python 3.10+
- `torch`
- `simpletransformers`
- `numpy`
- `pandas`

Puedes instalar las bibliotecas necesarias utilizando:

```bash
pip install torch simpletransformers numpy pandas
```

## Uso

1. **Configurar el Entorno**  
   Asegúrate de que Python y las bibliotecas requeridas estén instalados. Verifica que CUDA esté disponible si planeas usar la aceleración por GPU.

   ```python
   import torch
   if torch.cuda.is_available():
       print(f"CUDA está disponible. Número de dispositivos: {torch.cuda.device_count()}")
       for i in range(torch.cuda.device_count()):
           print(f"Dispositivo {i}: {torch.cuda.get_device_name(i)}")
   else:
       print("CUDA no está disponible.")
   ```

2. **Ejecutar el Notebook**  
   Abre el archivo de Jupyter Notebook proporcionado `smishing_detection_SimpleTransformers.ipynb` y ejecuta las celdas de manera secuencial. Ajusta las rutas y configuraciones según sea necesario.

## Nota sobre CUDA

La configuración relacionada con CUDA es detectada automáticamente por PyTorch. Sin embargo, asegúrate de:

- Tener instalados los controladores NVIDIA adecuados.
- Que la versión de CUDA sea compatible con tu instalación de PyTorch.

Si necesitas ajustar manualmente CUDA, modifica las secciones relevantes en el notebook.

## Conjunto de Datos

El proyecto espera un conjunto de datos de SMS con el siguiente formato:

| text                |   label  |
|---------------------|----------|
| "Este es un mensaje de prueba." | Bank    |
| "¡Has ganado un premio!"       | Delivery |




