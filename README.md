Arquitectura Funcional de alta disponibilidad en AWS

1. Descripción General
La solución se diseñó bajo los principios de alta disponibilidad, modularidad y automatización.
Cada capa —red, aplicación, datos e integración— está separada lógicamente para facilitar despliegues independientes y futuras ampliaciones.
La plantilla de CloudFormation parametriza las variables críticas, garantizando reproducibilidad y consistencia entre entornos.

2. Componentes Principales
La base de la arquitectura es una VPC con cuatro subredes: dos públicas y dos privadas, distribuidas en dos zonas de disponibilidad.
•	Subredes públicas: alojan los Application Load Balancers (ALB) y el NAT Gateway.
•	Subredes privadas: contienen instancias backend y la base de datos RDS.
•	Internet Gateway (IGW) y rutas: permiten salida a Internet sólo para servicios públicos.
•	NAT Gateway: habilita actualizaciones del sistema operativo en instancias privadas sin exponerlas públicamente.
Este diseño garantiza aislamiento y resiliencia ante fallos de zona.
