# Generación de imágenes — Carlos (actividad 73208)

Informe y código de dos prácticas generativas: una DCGAN no condicionada sobre CIFAR-10 y un ajuste LoRA de Stable Diffusion con descripciones derivadas de categorías de Fashion-MNIST.

## Archivos

Docente de la actividad: Nidia Stella García Roa.

- `main.tex`: informe APA en LaTeX.
- `Carlos_DCGAN_CIFAR10.ipynb`: DCGAN de 64 × 64 para Colab GPU.
- `Carlos_Diffusers_LoRA_FashionMNIST.ipynb`: ajuste LoRA exploratorio de 200 pasos sobre una muestra balanceada de Fashion-MNIST; requiere GPU; el checkpoint base es público y se descarga sin token. No usa el conjunto Pokémon, que muestra un aviso de retiro y exige solicitar acceso.
- `gan_core.py` y `experimento_digitos.py`: GAN introductoria reproducible en NumPy.
- `resultados_carlos/`: resultados medidos de esta versión de la GAN introductoria.

## Estado de las ejecuciones y evidencias

La GAN introductoria produce evidencia local en dígitos de 8 × 8. La DCGAN se ejecutó en Colab con GPU T4: usó 5.000 imágenes de CIFAR-10, completó 3 épocas de 78 lotes y guardó cuadrículas, pérdidas y checkpoint en `/content/resultados_dcgan_cifar10`. Las pérdidas finales por época fueron D = 0.365, 0.028 y 0.010; G = 2.457, 4.561 y 5.600. Son resultados de una corrida breve y no prueban calidad o diversidad visual.

El informe registra una ejecución LoRA en Colab con GPU Tesla T4, 500 imágenes de Fashion-MNIST (50 por clase), 200 pasos, semilla 42 y pérdida final de 0,0263. La comparación descrita usa el mismo prompt, semilla 42, 25 pasos y escala de guía 7,0 para ambas inferencias. Sin embargo, los archivos `base.png`, `lora.png` y `comparacion.png` de esa corrida todavía no están incluidos en este repositorio; tampoco está incluido el adaptador. Por eso, aquí no se pueden inspeccionar ni verificar visualmente esas salidas. El cuaderno guarda esos archivos en `/content/resultados_lora_carlos/` al ejecutar el bloque de comparación. Cuando se recuperen del entorno de Colab, deben añadirse a esa carpeta del repositorio para que la evidencia acompañe al informe. No se han sustituido por imágenes recreadas ni por resultados de otra ejecución.

## Ejecución local de la línea base

```bash
python experimento_digitos.py
```

No subir tokens, checkpoints privados ni archivos de rostro/personas a un repositorio. Revisar licencias de modelo y datos antes de redistribuir material.
