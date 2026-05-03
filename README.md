# Práctica 4 - Computación de Alto Rendimiento

## Estructura del repositorio

Este repositorio contiene el desarrollo completo de la práctica, incluyendo el código, resultados experimentales y la memoria final.

* **Task0/**
  Código base inicial proporcionado en la práctica.

* **Task1/**
  Versión intermedia del código donde se han realizado primeras modificaciones.

* **Task1Paralelizada/**
  Versión final del programa con paralelización mediante OpenMP y ejecución concurrente con `std::async`.

* **Resultados/**
  Contiene capturas de las ejecuciones del programa:

  * `secuencial/`: ejecución con 1 hilo
  * `paralelo/`: ejecución con múltiples hilos, incluyendo escalado y variación del tamaño de imagen

* **Gráficas/**
  Gráficas utilizadas en la memoria:

  * comparación de tiempos
  * speed-up
  * eficiencia
  * escalabilidad (hilos y tamaño de imagen)

* **InformeP4.pdf**
  Memoria completa de la práctica con explicación, resultados y conclusiones.

* **.gitignore**
  Archivo para evitar subir archivos innecesarios como `build/` o archivos compilados.

---

## Compilación y ejecución

Desde la carpeta del código (por ejemplo, dentro de `Task1Paralelizada`):

```bash
cmake -S src -B build
cd build
make
./detect ../compressions.png
```

---

## Paralelismo

El programa utiliza:

* **OpenMP** para paralelizar el procesamiento interno (especialmente en el algoritmo DCT)
* **std::async** para ejecutar distintas tareas en paralelo

Para cambiar el número de hilos:

```bash
export OMP_NUM_THREADS=4
```

---

## Resultados

Se han realizado experimentos para analizar:

* Comparación entre versión secuencial y paralela
* Speed-up y eficiencia
* Influencia del número de hilos
* Influencia del tamaño de la imagen

Los resultados se encuentran en:

* `Resultados/`
* `Gráficas/`

---

## Descripción general

Se ha paralelizado principalmente el algoritmo DCT, distribuyendo el procesamiento de bloques entre múltiples hilos. Además, se ha evaluado el rendimiento del programa bajo distintas condiciones para analizar su escalabilidad.

---

## Conclusión

El uso de paralelismo ha permitido mejorar significativamente el rendimiento en tareas computacionalmente intensivas, especialmente en el DCT, mostrando un speed-up notable y buen aprovechamiento de los recursos del sistema.

---
