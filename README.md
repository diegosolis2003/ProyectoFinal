# Proyecto Final de Electrónica 2 y Diseño Electrónico 1 - PCIe to USB & SATA / M.2 Bridge

<p align="center">
  <img src="PNG/Escudo-UNIS.png" alt="Escudo de la Universidad" width="200">
</p>
<p align="center">
  <em>Universidad del Istmo de Guatemala</em><br>
  <em>Facultad de Ingeniería</em><br>
  <em>Proyecto Final</em><br>
  <em>Electrónica 2 y Diseño Electrónico 1</em>
</p>
<p align="center">
  <em>Diego Fernando Solís López</em><br>
  <em>mayo de 2026</em>
</p>

---

## Descripción general
Este repositorio documenta el diseño de una tarjeta basada en PCIe to USB & Bridge a SATA y M.2, utilizando el chip **PCI11400** como núcleo principal. 

El objetivo del proyecto fue adaptar un diseño de referencia (EVB) hacia una solución funcional que permitiera la conversión e interconexión entre PCIe y diferentes interfaces. Durante el desarrollo se trabajó en:

* Captura esquemática
* Planeación de señales PCIe
* Arquitectura de potencia
* Manejo de señales auxiliares (reset, clock, presence)
* Consideraciones de diseño de alta velocidad

**Es importante notar que el diseño no fue completado en su totalidad**, especialmente en la implementación completa de PCIe y USB.

## Tabla de Contenido
1. [Descripción general](#descripción-general)
2. [Chip PCIe principal](#chip-pcie-principal)
3. [Objetivos del proyecto](#objetivos-del-proyecto)
4. [Arquitectura general](#arquitectura-general)
5. [Bloques principales del diseño](#bloques-principales-del-diseño)
6. [Filosofía de diseño](#filosofía-de-diseño)
7. [Herramientas utilizadas](#herramientas-utilizadas)
8. [Estado actual](#estado-actual)
9. [Notas](#notas)

## Chip PCIe principal
El diseño está basado en el **PCI11400**, un controlador orientado a aplicaciones PCIe con soporte para múltiples interfaces. En este proyecto se utiliza como puente para conectar:

* PCIe ↔ USB
* PCIe ↔ SATA
* PCIe ↔ M.2

**Características consideradas:**
* Manejo de enlaces PCIe
* Soporte para múltiples interfaces downstream
* Configuración mediante señales de control
* Integración con buses auxiliares

## Objetivos del proyecto
* Diseñar una tarjeta basada en PCIe capaz de interactuar con USB, SATA y M.2.
* Adaptar el diseño EVB del PCI11400.
* Simplificar el sistema eliminando módulos no necesarios.
* Aplicar buenas prácticas de diseño.
* Desarrollar una PCB funcional.

## Arquitectura general

```text
       Host PCIe
           |
           | PCIe
           |
+----------------------+
|      PCI11400        |
+----------------------+
   |       |       |
   |       |       |
  USB     SATA    M.2

El chip PCI11400 actúa como puente entre el host PCIe y múltiples interfaces de salida.

Bloques principales del diseño
1. Interfaz PCIe upstream
Conexión principal hacia el host mediante pares diferenciales TX/RX, reloj y señales de control.

2. Núcleo PCI11400
Componente central encargado de gestionar la comunicación entre interfaces.

3. Interfaces downstream
Incluyen conexiones hacia:

USB (no completado)

SATA (parcial)

M.2 (parcial)

4. Arquitectura de potencia
Distribución de voltajes necesarios con regulación simplificada respecto al EVB.

5. Señales auxiliares
PERST#

CLK

WAKE#

PRSNT#

Filosofía de diseño
El proyecto sigue el diseño de referencia EVB, pero enfocado en simplificación:

Eliminación total de UART.

Reducción de interfaces innecesarias.

Menor complejidad de ruteo.

Enfoque en aprendizaje práctico.

Herramientas utilizadas
Capture CIS de OrCAD

OrCAD Allegro

Datasheets del PCI11400

Documentación EVB

Estado actual
El proyecto alcanzó aproximadamente un 60% – 70% de desarrollo.

Debido a dificultades durante el proceso:

No se completó la implementación de PCIe.

No se finalizó la integración USB.

Interfaces SATA y M.2 quedaron parciales.

Sin embargo, se logró:

Aplicar buenas prácticas de diseño.

Comprender la arquitectura PCIe.

Desarrollar una base sólida del sistema.

Notas
Este proyecto es de carácter académico. Antes de una implementación real se deben validar:

Señales de alta velocidad

Integridad de potencia

Ruteo diferencial

Configuración completa del PCIe
