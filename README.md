# Redes Profundas y Aprendizaje de Máquina

Este repositorio contiene las prácticas, arquitecturas de redes neuronales y modelos de aprendizaje profundo desarrollados para el curso.

## 📋 Descripción
El objetivo de este proyecto es implementar y evaluar modelos de Deep Learning (clasificación, redes convolucionales, etc.) analizando su desempeño y ajuste de hiperparámetros.

## 🚀 Requisitos e Instalación
El notebook se ejecuta en un ambiente de conda llamado `deep-pytorch` con Python 3.14 y PyTorch 2.14.1. Los comandos siguientes son para PowerShell en Windows.

**Requisito previo:** tener [Miniconda](https://docs.conda.io/en/latest/miniconda.html) instalado. Si es la primera vez que se usa conda en PowerShell, ejecutar una vez `conda init powershell` y luego cerrar y volver a abrir PowerShell. Si aparece un error de "ejecución de scripts deshabilitada", ejecutar:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

### 1. Crear el ambiente

```powershell
conda create -n deep-pytorch python=3.14 -y
conda activate deep-pytorch
```

### 2. Instalar PyTorch
Ejecutar `nvidia-smi` y revisar el valor `CUDA Version` (esquina superior derecha). Usar **solo una** de las siguientes líneas:

```powershell
# CUDA Version 13.x
pip install torch==2.14.1 torchvision==0.29.1 --index-url https://download.pytorch.org/whl/cu130

# CUDA Version 12.6 a 12.9
pip install torch==2.14.1 torchvision==0.29.1 --index-url https://download.pytorch.org/whl/cu126

# Sin tarjeta NVIDIA o si nvidia-smi no existe (solo CPU, el entrenamiento es mucho más lento)
pip install torch==2.14.1 torchvision==0.29.1 --index-url https://download.pytorch.org/whl/cpu
```

### 3. Instalar las demás bibliotecas
Desde la carpeta del repositorio, y **solo después del paso 2** (si se hace antes, pip instala la versión de PyTorch sin GPU):

```powershell
pip install -r requirements.txt
```

Para verificar que PyTorch detecta la GPU (debe imprimir `True` si se instaló la versión con CUDA):

```powershell
python -c "import torch; print(torch.__version__, torch.cuda.is_available())"
```

## ▶️ Ejecución del notebook
1. Copiar el dataset comprimido con el nombre `Brain_Tumor_MRI_Dataset.zip` en la misma carpeta que `MiniProyecto1.ipynb`. El notebook lo descomprime en `./Brain_Tumor_Data`.
2. Abrir `MiniProyecto1.ipynb` en VS Code y, en **Select Kernel**, elegir el ambiente `deep-pytorch`.
3. Ejecutar las celdas en orden.
