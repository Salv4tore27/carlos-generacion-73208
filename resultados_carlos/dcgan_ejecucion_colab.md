# Registro de ejecución DCGAN en Colab

- Notebook: `Carlos_DCGAN_CIFAR10.ipynb`
- Entorno: GPU T4; PyTorch 2.14.1+cu130
- Conjunto: CIFAR-10; subconjunto aleatorio de 5.000 imágenes, semilla 73
- Tamaño: 64 × 64 RGB; lote 64; 78 lotes por época
- Entrenamiento completado: 3 épocas
- Pérdidas impresas al cierre de cada época: D = 0.365, 0.028, 0.010; G = 2.457, 4.561, 5.600
- Colab guardó `epoca_1.png`, `epoca_2.png`, `epoca_3.png`, `evolucion.png`, `perdidas.png` y `dcgan_cifar10.pt` en `/content/resultados_dcgan_cifar10`.

El runtime ejecutó la práctica, pero no se logró transferir estos archivos generados a este paquete local; Colab los conserva solo durante la sesión. El CSV contiene los valores del registro visible de Colab. No usarlo como evidencia de calidad visual. El desequilibrio de pérdidas justifica más épocas y evaluación de diversidad antes de concluir que la DCGAN aprendió representaciones útiles.
