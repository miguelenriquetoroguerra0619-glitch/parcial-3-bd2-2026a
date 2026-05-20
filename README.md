# Proyecto integrador — Parcial 3
## Bases de Datos 2 · Unipaz · Cuarto semestre

Este repositorio contiene los **12 enunciados de proyecto** del corte 3 de la asignatura **Bases de Datos 2**, junto con las normas de entrega y el flujo de trabajo con GitHub.

---

## 1. Propósito

Integrar lo aprendido este semestre (DDL, DML, normalización hasta 3FN) con lo visto en semestres anteriores (lógica computacional, POO, estructuras de datos y bases de datos 1) en un aplicativo funcional que use una base de datos relacional real.

## 2. Modalidad

- **24 estudiantes**, **12 proyectos**, modalidad **individual**.
- Cada proyecto será desarrollado por **dos estudiantes distintos**, generando **dos versiones** independientes del mismo enunciado.
- Habrá **doble evaluación**:
  1. **Calificación docente** (técnica y de la asignatura): centrada en BD.
  2. **Calificación apreciativa entre pares**: el grupo elige la mejor versión de cada proyecto.

## 3. Reglas técnicas

- **Motor de BD obligatorio**: MySQL o PostgreSQL. Nada de SQLite ni archivos planos.
- **Lenguaje del aplicativo**: libre (Java, Python, C#, JavaScript/Node, PHP, etc.).
- **Tipo de aplicación**: libre (escritorio o web).
- **El aplicativo debe usar realmente la BD** (lecturas y escrituras durante la sustentación).
- **Normalización mínima exigida**: 3FN.

## 4. Entregables (los 12 por igual)

1. **Aplicativo funcionando** ejecutable durante la sustentación.
2. **Diagrama MER completo**, con entidades, atributos, **PK, FK y cardinalidades**.
3. **Script DDL** (`.sql`) que crea la base de datos desde cero.
4. **Datos de prueba mínimos** (script DML) que permitan sustentar el aplicativo.
5. **README propio** dentro de la carpeta de entrega, con instrucciones de instalación y ejecución.

## 5. Rúbrica de evaluación docente

| Criterio | Peso |
|---|---|
| MER completo, correcto y normalizado hasta 3FN (PK, FK, cardinalidades) | 40% |
| Aplicativo funcionando y usando realmente la BD | 35% |
| Cumplimiento de los requisitos funcionales mínimos del enunciado | 20% |
| Sustentación clara del diseño de BD | 5% |

> El código en sí no es el foco de la evaluación: lo importante es que el aplicativo funcione y que la BD esté bien diseñada y usada.

## 6. Listado de proyectos

Los enunciados completos están en la carpeta [`proyectos/`](./proyectos/). Lectura obligatoria del enunciado asignado.

| # | Proyecto | Resumen |
|---|---|---|
| 01 | [Inmobiliaria de arrendamientos](./proyectos/proyecto-01-inmobiliaria.md) | Inmuebles, propietarios, arrendatarios, contratos, cuotas y mora. |
| 02 | [Farmacia de barrio](./proyectos/proyecto-02-farmacia.md) | Productos, lotes con vencimiento, ventas y compras a proveedores. |
| 03 | [Reservas de restaurante](./proyectos/proyecto-03-reservas-restaurante.md) | Mesas, reservas con validación de horario, órdenes y carta. |
| 04 | [Citas médicas en consultorio](./proyectos/proyecto-04-citas-medicas.md) | Pacientes, médicos por especialidad, agenda y consultas. |
| 05 | [Venta de boletos de cine](./proyectos/proyecto-05-cine.md) | Películas, salas, funciones y venta de boletos por butaca. |
| 06 | [Control de parqueadero](./proyectos/proyecto-06-parqueadero.md) | Ingresos, cobro por tiempo y clientes mensuales con cupo. |
| 07 | [Gestión de gimnasio](./proyectos/proyecto-07-gimnasio.md) | Afiliados, membresías, clases dirigidas y asistencia. |
| 08 | [Hotel pequeño](./proyectos/proyecto-08-hotel.md) | Habitaciones, reservas por rango, check-in/out y consumos. |
| 09 | [Gestión de eventos académicos](./proyectos/proyecto-09-eventos-academicos.md) | Eventos, ponentes, asistentes, asistencia y certificados. |
| 10 | [Tienda online básica](./proyectos/proyecto-10-tienda-online.md) | Catálogo, carrito, pedidos y estados de pedido. |
| 11 | [Taller mecánico](./proyectos/proyecto-11-taller-mecanico.md) | Vehículos, órdenes de trabajo, mecánicos y repuestos. |
| 12 | [Veterinaria](./proyectos/proyecto-12-veterinaria.md) | Mascotas, consultas, aplicación de vacunas y tratamientos. |

## 7. Flujo de trabajo con GitHub

El trabajo se entrega mediante **fork + rama + pull request**.

### Paso a paso para el estudiante

1. **Hacer fork** de este repositorio a tu cuenta personal de GitHub.
2. **Clonar tu fork** localmente:
   ```bash
   git clone https://github.com/<tu-usuario>/parcial-3-bd2.git
   cd parcial-3-bd2
   ```
3. **Crear una rama** con un nombre claro:
   ```bash
   git checkout -b entrega/nombre-apellido-proyectoXX
   ```
   Ejemplo: `entrega/juan-perez-proyecto03`.
4. **Crear tu carpeta** dentro de `entregas/`:
   ```
   entregas/nombre-apellido-proyectoXX/
   ```
5. **Trabajar tu proyecto** dentro de esa carpeta (ver estructura sugerida abajo).
6. **Hacer commits** frecuentes con mensajes claros:
   ```bash
   git add entregas/nombre-apellido-proyectoXX
   git commit -m "DDL inicial: tablas principales con PK y FK"
   git push origin entrega/nombre-apellido-proyectoXX
   ```
7. **Abrir un Pull Request** desde tu rama hacia la rama `main` del repositorio original cuando hayas terminado.
8. El PR debe titularse: `Entrega - Nombre Apellido - Proyecto XX`.

### Estructura sugerida dentro de tu carpeta

```
entregas/nombre-apellido-proyectoXX/
├── README.md         ← cómo instalar y correr TU aplicativo
├── mer/
│   ├── diagrama.png  (o .pdf)
│   └── notas-normalizacion.md
├── ddl/
│   ├── 01-crear-bd.sql
│   └── 02-datos-prueba.sql
└── app/
    └── (código fuente del aplicativo)
```

### Reglas para tu PR

- Solo modifica archivos **dentro de tu carpeta**. No edites los enunciados ni la entrega de otro estudiante.
- No subas binarios pesados, ejecutables compilados, ni la BD `.mysql`/`.pgdata`. Sí el script `.sql`.
- No subas archivos de configuración local con contraseñas (`.env`, `config.json` con credenciales).
- Incluye en el `README.md` de tu entrega: cómo crear la BD, cómo cargar datos de prueba, cómo correr el aplicativo y un usuario de prueba para la sustentación.

## 8. Calificación apreciativa entre pares

Al cierre del corte, cada estudiante verá las dos versiones de cada proyecto (la suya y la del compañero asignado al mismo enunciado) revisando los forks o las carpetas en `entregas/`. El grupo votará la mejor versión por proyecto. Este puntaje complementa la calificación docente.

## 9. Fechas y plazos

- **Asignación de proyectos**: por confirmar.
- **Fecha límite de PR**: por confirmar.
- **Sustentaciones**: por confirmar.

> Las fechas se publicarán en este mismo README.

## 10. Preguntas

Cualquier duda sobre un enunciado, abrir un **issue** en este repositorio (no por mensaje privado). Esto permite que la respuesta llegue a todo el grupo.

---

*Asignatura: Bases de Datos 2 — Unipaz — Cuarto semestre.*
