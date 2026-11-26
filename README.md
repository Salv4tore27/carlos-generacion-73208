# Generación de imágenes — Carlos (actividad 73208)

Informe y código de dos prácticas generativas: una DCGAN no condicionada sobre CIFAR-10 y un ajuste LoRA de Stable Diffusion con captions de Pokémon.

## Archivos

- `main.tex`: informe APA en LaTeX.
- `Carlos_DCGAN_CIFAR10.ipynb`: DCGAN de 64 × 64 para Colab GPU.
- `Carlos_Diffusers_LoRA_Pokemon.ipynb`: ajuste LoRA exploratorio de 300 pasos; requiere GPU, aceptación de licencia de Stable Diffusion v1.5 y `HF_TOKEN` guardado en Secretos de Colab.
- `gan_core.py` y `experimento_digitos.py`: GAN introductoria reproducible en NumPy.
- `resultados_carlos/`: resultados medidos de esta versión de la GAN introductoria.

## Estado honesto

La GAN introductoria produce evidencia local en dígitos de 8 × 8. Los cuadernos DCGAN-CIFAR-10 y LoRA están preparados, pero **no se han ejecutado en Colab**; faltan sus imágenes generadas, curvas, registros y análisis posterior. El informe marca estos resultados como pendientes y no inventa salidas. Ejecutar cada cuaderno de principio a fin y descargar `/content/resultados_dcgan_cifar10` y `/content/resultados_lora_carlos` antes de entregar como práctica completa.

## Ejecución local de la línea base

```bash
python experimento_digitos.py
```

No subir tokens, checkpoints privados ni archivos de rostro/personas a un repositorio. Revisar licencias de modelo y datos antes de redistribuir material.
