# Generación de imágenes — Carlos (actividad 73208)

Informe y código de dos prácticas generativas: una DCGAN no condicionada sobre CIFAR-10 y un ajuste LoRA de Stable Diffusion con descripciones derivadas de categorías de Fashion-MNIST.

## Archivos

Docente de la actividad: Nidia Stella García Roa.

- `main.tex`: informe APA en LaTeX.
- `Carlos_DCGAN_CIFAR10.ipynb`: DCGAN de 64 × 64 para Colab GPU.
- `Carlos_Diffusers_LoRA_FashionMNIST.ipynb`: ajuste LoRA exploratorio de 200 pasos sobre una muestra balanceada de Fashion-MNIST; requiere GPU; el checkpoint base es público y se descarga sin token. No usa el conjunto Pokémon, que muestra un aviso de retiro y exige solicitar acceso.
- `gan_core.py` y `experimento_digitos.py`: GAN introductoria reproducible en NumPy.
- `resultados_carlos/`: resultados medidos de esta versión de la GAN introductoria.
- `resultados_lora/`: imágenes base y adaptada, comparación visual y registro de la ejecución LoRA en Colab.
- `pesos_lora/pytorch_lora_weights.safetensors`: adaptador entrenado; revisar CreativeML OpenRAIL-M antes de redistribuirlo.

## Estado de las ejecuciones y evidencias

La GAN introductoria produce evidencia local en dígitos de 8 × 8. La DCGAN se ejecutó en Colab con GPU T4: usó 5.000 imágenes de CIFAR-10, completó 3 épocas de 78 lotes y guardó cuadrículas, pérdidas y checkpoint en `/content/resultados_dcgan_cifar10`. Las pérdidas finales por época fueron D = 0.365, 0.028 y 0.010; G = 2.457, 4.561 y 5.600. Son resultados de una corrida breve y no prueban calidad o diversidad visual.

El informe registra una ejecución LoRA en Colab con GPU Tesla T4, 500 imágenes de Fashion-MNIST (50 por clase), 200 pasos y semilla 42. El cuaderno genera `base.png`, `lora.png` y `comparacion.png` con el mismo prompt, 25 pasos y escala de guía 7,0 para ambas inferencias. Las salidas reales y el registro están en `resultados_lora/`; el adaptador entrenado está en `pesos_lora/`. En la comparación, la salida LoRA conserva la silueta del calzado pero se ve más difusa que la base. Es una observación cualitativa de un prompt y una semilla, no una medida de mejora general. El entrenamiento finalizó 200 pasos en una T4; la pérdida debe interpretarse solo como valor de optimización, no como métrica perceptual. El checkpoint usa la licencia CreativeML OpenRAIL-M: revise sus condiciones antes de redistribuir los pesos o derivados.

## Ejecución local de la línea base

```bash
python experimento_digitos.py
```

No subir tokens, checkpoints privados ni archivos de rostro/personas a un repositorio. Revisar licencias de modelo y datos antes de redistribuir material.
