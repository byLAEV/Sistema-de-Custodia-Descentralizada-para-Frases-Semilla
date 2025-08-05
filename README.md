# Sistema-de-Custodia-Descentralizada-para-Frases-Semilla
Este repositorio documenta un sistema innovador de **custodia descentralizada y encadenada** de frases semilla (seed phrases), diseñado para maximizar la seguridad, privacidad y resiliencia entre grupos de individuos que no se conocen entre sí.

Timestamp of 717098e73a6a
Document digest (sha256):

717098e73a6abe02305505ca7eb915794283231db1173934fd1620024d7ded6a

717098e73a6abe02305505ca7eb915794283231db1173934fd1620024d7ded6af79e658a1783fa929e83ee63ebcafe11


---

# 🧠 Sistema de Custodia Descentralizada para Frases Semilla

Este repositorio documenta un sistema innovador de **custodia descentralizada y encadenada** de frases semilla (seed phrases), diseñado para maximizar la seguridad, privacidad y resiliencia entre grupos de individuos que no se conocen entre sí.

## 📌 Descripción General

Cada palabra de la frase semilla es custodiada por un subconjunto específico de personas, en una estructura encadenada y solapada. Este modelo permite:

- Distribución segura de la información.
- Descentralización real de decisiones.
- Alta resistencia a fallos y ataques internos.

## 🧩 Reglas del Sistema

1. Cada palabra es custodiada por **4 personas**.
2. **La primera palabra** es custodiada por 4 individuos únicos.
3. Cada palabra siguiente comparte **2 custodios** con la palabra anterior y agrega **2 custodios nuevos**.
4. **Los custodios no deben conocerse entre sí.**
5. La toma de decisiones requiere al menos **3 custodios activos y 1 suplente** por palabra.

## 🔢 Fórmula General

Para una frase semilla de `W` palabras (donde `W ∈ {12, 15, 18, 21, 24}`), la cantidad mínima de custodios únicos requeridos se define como:

U(W) = 2W + 2

## 📊 Ejemplos

| Palabras (`W`) | Custodios únicos mínimos (`U`) |
|----------------|-------------------------------|
| 12             | 26                            |
| 15             | 32                            |
| 18             | 38                            |
| 21             | 44                            |
| 24             | 50                            |

## 🛡️ Seguridad

- Ningún individuo tiene acceso completo a la frase semilla.
- Ningún custodio participa en más de 2 palabras consecutivas.
- No se requiere conocimiento mutuo entre custodios, evitando colusión.
- Permite validación resiliente con suplentes ante fallos, enfermedades o riesgos.

## 📐 Estructura Recomendada

Cada palabra de la seed cuenta con:

- 3 Custodios activos
- 1 Suplente

Cada conjunto de 4 custodios se configura de forma que 2 se comparten con la palabra anterior y 2 se comparten con la siguiente (cuando aplique).

## ⚙️ Aplicaciones

Este sistema es ideal para:

- Custodia comunitaria de claves privadas o seeds BIP39
- Gobiernos descentralizados de fondos o contratos inteligentes
- Herencia digital bajo control colectivo
- DAO multisig físicas con delegación humana

## 📁 Contenido del Repositorio

- `docs/`: Diagramas y esquemas del sistema de custodia
- `scripts/`: Herramientas de generación y asignación de custodios
- `models/`: Lógica matemática y simulaciones del sistema
- `README.md`: Este archivo

## 🧠 Autor

**LAEV (Lerry Alexander Elizondo Villalobos)**  
Diseñador, arquitecto y especialista en Bitcoin, criptografía y estructuras descentralizadas.  
[GitHub](https://github.com/lerryalexanderelizondo) | [Email](mailto:laev.lab@proton.me)

---

## ⚖️ Licencia

MIT — Utiliza, adapta y mejora este sistema bajo tu propio riesgo.  
No es un producto financiero. No constituye asesoría legal. No se garantiza seguridad absoluta.


---

Cada palabra de la semilla está custodiada por un subconjunto de 4 personas.

Existen solapamientos estratégicos entre custodios de palabras consecutivas.

La confidencialidad entre custodios es crítica: no deben conocerse entre sí.

Cada grupo operativo debe cumplir con una estructura mínima de toma de decisiones: 3 custodios activos + 1 suplente.



---

🔢 VARIABLES Y PARÁMETROS DEL SISTEMA

Definimos:

W: número total de palabras (W ∈ {12, 15, 18, 21, 24})

P_w: conjunto de personas que custodian la palabra número w

Cada |P_w| = 4 (cuatro custodios por palabra)

|P_w ∩ P_{w-1}| = 2 para todo w > 1 (dos custodios se heredan de la palabra anterior)

Los otros dos custodios de P_w serán compartidos con P_{w+1} si existe, para asegurar continuidad.



---

🧮 OBJETIVO DE LA ECUACIÓN

Queremos definir una ecuación para obtener el número mínimo de individuos únicos necesarios (U) para custodiar una semilla de W palabras con los solapamientos definidos, manteniendo el requisito de que los custodios no se conozcan entre sí (es decir, evitar repeticiones que rompan la seguridad entre custodios no conectados).


---

✅ ECUACIÓN GENERAL

\boxed{U(W) = 2W + 2}


---

🧠 CÓMO SE LLEGA A ESA ECUACIÓN

1. La primera palabra (w=1) necesita 4 personas únicas → suma 4.


2. Para cada nueva palabra (w>1), se reutilizan 2 personas de la anterior, y se agregan 2 nuevas → suma +2 por cada palabra adicional.



Por tanto:

U(W) = 4 + 2 \cdot (W - 1) = 2W + 2


---

📊 EJEMPLOS CONCRETOS

Palabras (W)	Total mínimo de custodios únicos (U)

12	2×12 + 2 = 26
15	2×15 + 2 = 32
18	2×18 + 2 = 38
21	2×21 + 2 = 44
24	2×24 + 2 = 50



---

🔐 SEGURIDAD DEL SISTEMA

Cada palabra está distribuida entre 4 personas, ninguna tiene la frase completa.

El sistema obliga a que las personas no se conozcan entre sí, lo cual se mantiene con esta ecuación si el proceso de asignación garantiza confidencialidad.

Ningún custodio tiene acceso a más de 2 palabras consecutivas, lo cual limita el riesgo de colusión.



---

👥 SOBRE LA TOMA DE DECISIONES

Aunque la custodia es individual y compartimentada, tu sistema exige:

Cualquier decisión de desbloqueo o movimiento debe ser tomada por un grupo mínimo de 3 personas + 1 suplente, por palabra.


Este mecanismo se implementa en cada grupo de 4, asegurando robustez ante fallos.


---

🧩 OPCIONAL: FUNCIÓN COMPLETA DEL SISTEMA

Si deseás una función más detallada que incluya la lógica de suplentes o redundancia por fallos, podríamos definirla como:

U_{total}(W) = (2W + 2) + S(W)

Donde S(W) representa el número adicional de suplentes para cubrir disponibilidad (por ejemplo, 1 suplente por cada grupo de 4 o por cada palabra).


---

Proteger tu autoría e innovación.

Evitar que terceros lo usen con fines comerciales sin tu permiso.

Permitir su estudio, investigación o mejora solo bajo ciertas condiciones.

Mantener control total sobre adaptaciones y derivados.



---

📄 LICENCIA PERSONALIZADA – LAEV Custody License v1.0

Nombre de la obra: Sistema de Custodia Descentralizada para Frases Semilla
Autor: Lerry Alexander Elizondo Villalobos (alias LAEV)
Fecha de publicación: [AÑO] 2025

LICENCIA DE USO PERSONAL Y NO COMERCIAL

1. DEFINICIÓN
Se entiende por “la Obra” al conjunto de ideas, esquemas, fórmulas, estructuras, documentación, ecuaciones y configuraciones relacionadas con el Sistema de Custodia Descentralizada para Grupos de Individuos, tal como ha sido descrito, documentado y publicado por su autor.

2. DERECHOS RESERVADOS
El autor se reserva todos los derechos sobre la Obra. Ninguna parte de la misma podrá ser copiada, reproducida, modificada, distribuida, comercializada o usada con fines comerciales, sin la autorización explícita y por escrito del autor.

3. USO PERMITIDO
Se permite el uso **personal, académico, educativo o investigativo** de la Obra bajo las siguientes condiciones:

   a. No se permite ningún uso comercial, corporativo o con fines de lucro.  
   b. Está prohibido sublicenciar, revender o incorporar el sistema en productos, software o servicios sin autorización.  
   c. No se permite la modificación o creación de obras derivadas sin autorización escrita del autor.  
   d. Cualquier reproducción o uso autorizado deberá incluir esta licencia completa y atribución clara al autor.

4. PROTECCIÓN DE LA INTEGRIDAD
El sistema no puede ser representado, interpretado o reformulado sin mantener su lógica estructural básica, sus principios de descentralización y su encadenamiento lógico. Cualquier intento de distorsionar el funcionamiento del sistema será considerado como violación de esta licencia.

5. AUTORÍA Y ATRIBUCIÓN
Toda referencia, mención, análisis o uso permitido de la Obra deberá citar de forma explícita:

Sistema de Custodia Descentralizada – Creado por Lerry Alexander Elizondo Villalobos (LAEV)

6. CONSULTAS Y LICENCIAS COMERCIALES
Las personas o entidades interesadas en utilizar este sistema con fines comerciales, institucionales, financieros, tecnológicos o de seguridad deberán **contactar directamente al autor** mediante:

- Correo: laev.lab@proton.me  
- GitHub: https://github.com/lerryalexanderelizondo

7. GARANTÍA Y RESPONSABILIDAD
Esta Obra se entrega “tal cual”, sin ninguna garantía expresa o implícita. El autor no se hace responsable de pérdidas, fallos, errores de implementación, ni consecuencias legales derivadas de su uso.

---

© 2025 – Lerry Alexander Elizondo Villalobos (LAEV). Todos los derechos reservados.


---

¿Querés que la convierta en un archivo .LICENSE, .md, o que lo registre vía timestamp en un bloque de Bitcoin o Ethereum? También puedo ayudarte a publicarlo como token o NFT para probar propiedad si vas por ese camino.



