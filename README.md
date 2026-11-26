# Generación de imágenes — Carlos (actividad 73208)

Informe y código de dos prácticas generativas: una DCGAN no condicionada sobre CIFAR-10 y un ajuste LoRA de Stable Diffusion con descripciones derivadas de categorías de Fashion-MNIST.

## Archivos

- `main.tex`: informe APA en LaTeX.
- `Carlos_DCGAN_CIFAR10.ipynb`: DCGAN de 64 × 64 para Colab GPU.
- `Carlos_Diffusers_LoRA_FashionMNIST.ipynb`: ajuste LoRA exploratorio de 200 pasos sobre una muestra balanceada de Fashion-MNIST; requiere GPU; el checkpoint base es público y se descarga sin token. No usa el conjunto Pokémon, que muestra un aviso de retiro y exige solicitar acceso.
- `gan_core.py` y `experimento_digitos.py`: GAN introductoria reproducible en NumPy.
- `resultados_carlos/`: resultados medidos de esta versión de la GAN introductoria.

## Estado honesto

La GAN introductoria produce evidencia local en dígitos de 8 × 8. La DCGAN se ejecutó en Colab con GPU T4: usó 5.000 imágenes de CIFAR-10, completó 3 épocas de 78 lotes y guardó cuadrículas, pérdidas y checkpoint en `/content/resultados_dcgan_cifar10`. Las pérdidas finales por época fueron D = 0.365, 0.028 y 0.010; G = 2.457, 4.561 y 5.600. Son resultados de una corrida breve y no prueban calidad o diversidad visual. El cuaderno LoRA usa Fashion-MNIST y captions creados a partir de sus clases. Aún falta ejecutar los 200 pasos en Colab y revisar sus salidas antes de reportar resultados.

## Ejecución local de la línea base

```bash
python experimento_digitos.py
```

No subir tokens, checkpoints privados ni archivos de rostro/personas a un repositorio. Revisar licencias de modelo y datos antes de redistribuir material.
