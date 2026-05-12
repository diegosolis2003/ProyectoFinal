README – Proyecto PCI11400

Este proyecto se basa en el análisis y adaptación del diseño de referencia EVB-PCI11400 para su uso con el PCI-11400, enfocándose en simplificar la arquitectura y aplicar buenas prácticas de diseño electrónico.

Diseño original (EVB)

El diseño de referencia incluye:

PCIe x4 + x1
Interfaces múltiples: USB, UART, RS232/RS422/RS485
EEPROM (AT24C64)
Generación de reloj dedicada
Regulación multietapa (12V → 1.1V)

Se trata de una placa de evaluación completa, pensada para cubrir todos los casos de uso.

Implementación propia

En el desarrollo del proyecto:

Se simplificó el uso de PCIe (enfoque en configuración básica)
Se eliminaron interfaces no esenciales
No se implementó ningún módulo UART
Se redujo la complejidad en clock y regulación

Sin embargo:

El proyecto no fue completado en su totalidad, ya que quedaron pendientes:

Partes del diseño PCIe (integración completa y validación)
Implementación de interfaces USB

Avance del proyecto

Debido a las dificultades encontradas durante el desarrollo, el proyecto alcanza aproximadamente:

 60% – 70% de implementación total

A pesar de no haberse finalizado completamente, se logró:

Aplicar buenas prácticas de diseño
Comprender la arquitectura del sistema PCIe
Realizar una adaptación funcional del esquema original
Comparativa

Característica	EVB Original	Diseño propio
PCIe	x4 + x1	Parcial / simplificado
USB	Completo	❌ No implementado
UART	Incluido	❌ No utilizado
Interfaces	Muchas	Reducidas
Estado	Completo	Parcial
🧠 Conclusión

El EVB-PCI11400 representa un diseño completo y robusto, mientras que este proyecto constituye una implementación parcial optimizada, donde, a pesar de no haberse finalizado, se logró extraer
