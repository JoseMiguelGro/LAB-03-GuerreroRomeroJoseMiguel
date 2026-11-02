# Laboratorio 03 - Privacidad, cumplimiento y gobierno de los datos

- **Autor: Guerrero Romero Jose Miguel**
- **Grupo: 4-3**

## 1. Introducción
Este laboratorio aborda la privacidad y gobierno de datos en PostgreSQL, analizando cómo los principios de minimización, limitación de finalidad y retención se traducen en decisiones técnicas y controles de acceso, más allá de la simple seguridad perimetral de la base de datos.

## 2. Inventario de datos
Se clasificaron los datos almacenados determinando cuáles son personales (nombre, correo, teléfono, edad, ciudad, código postal) y personales sensibles/financieros (RFC). Se definió su necesidad y nivel de acceso requerido.

## 3. Finalidades
Los datos se dividieron según su propósito operativo: atención al cliente (contacto básico), facturación (RFC, domicilio) y analítica (edades, ubicaciones). No todos los datos deben estar disponibles para todos los propósitos.

## 4. Minimización
Se eliminaron campos innecesarios para roles específicos, como excluir el RFC y la edad de las tablas de soporte técnico, asegurando que los usuarios accedan solo a lo estrictamente indispensable.

## 5. Control de acceso
Se establecieron roles (ej. `analista`) y vistas (`v_analitica_clientes`) que aplican el principio de menor privilegio, permitiendo consultas agregadas sin exponer datos personales directos de la tabla original.

## 6. Derechos ARCO
Se identificaron las implicaciones técnicas: el derecho de acceso requiere conocer dónde residen los datos; la rectificación demanda trazabilidad (logs); la cancelación implica borrar también en respaldos, réplicas y sistemas exportados, no solo un `DELETE`; y la oposición puede requerir banderas lógicas (`opt_out`).

## 7. Retención
Se estableció que conservar datos indefinidamente "por si acaso" es un riesgo. El ciclo de vida debe contemplar obligaciones fiscales/legales y depurar o anonimizar información una vez cumplida su finalidad.

## 8. Gobierno de datos
Se creó una matriz asignando responsables y determinando quién puede acceder a qué, las medidas de protección y la retención aplicable, garantizando un control ordenado del ciclo de vida del dato.

## 9. Evaluación integral
Se detectaron riesgos graves como acceso irrestricto de analistas a tablas origen, copias a desarrollo con datos reales, retención indefinida y uso de correos sin consentimiento. Se propusieron soluciones técnicas como enmascaramiento y RLS.

## 10. Conclusiones
La seguridad de la información protege contra accesos no autorizados, pero la privacidad asegura que los accesos autorizados sean éticos y legales. El DBA debe colaborar con áreas jurídicas para traducir políticas en controles técnicos (vistas, enmascaramiento, segregación por esquemas) aplicando privacidad por diseño y por defecto.

---

## Preguntas de reflexión

1.  **¿Una base de datos técnicamente segura necesariamente cumple con todos los requisitos de privacidad?**
    No. Una base puede tener altos niveles de criptografía (seguridad técnica) pero recolectar información sensible no permitida por ley o conservarla sin justificación (violación de privacidad).
2.  **¿Por qué el principio de mínimo privilegio también contribuye a la privacidad?**
    Garantiza que un usuario reciba solo la información estrictamente necesaria y avalada para su rol, limitando la exposición.
3.  **¿Por qué el DBA no debería decidir por sí solo la finalidad del tratamiento de los datos?**
    El DBA desconoce el marco regulatorio (LFPDPPP) y los acuerdos contractuales; es competencia de los departamentos legales dictaminar el tratamiento legítimo.
4.  **¿Por qué los desarrolladores no deberían recibir automáticamente copias completas de bases de datos productivas?**
    Viola la minimización y expone datos personales reales en infraestructuras carentes de los candados que existen en producción.
5.  **¿Por qué una copia utilizada para desarrollo también puede representar un riesgo de privacidad?**
    Porque una fuga originada en el ambiente de desarrollo compromete la información confidencial de clientes reales.
6.  **¿Por qué la retención debe formar parte del ciclo de vida de los datos?**
    Porque los datos personales no deben subsistir indefinidamente. Su almacenamiento es legal solo mientras persista la finalidad que originó su obtención.
7.  **¿Qué relación existe entre privacidad por diseño y diseño de bases de datos?**
    Exige que la estructura misma (tablas limitadas, campos no obligatorios, roles restrictivos) se planifique desde la creación del esquema y no como un parche a posteriori.
8.  **¿Qué controles técnicos implementarías para reducir el riesgo de exposición de datos personales?**
    Vistas segregadas, enmascaramiento de columnas para roles no críticos, cifrado en reposo para identificadores sensibles y monitoreo de sentencias con `pgaudit`.
9.  **¿Qué información debería conocer un DBA para responder técnicamente a una solicitud ARCO?**
    El inventario exacto de en qué tablas reside el dato, los mecanismos de integridad referencial, y si el registro figura en repositorios de respaldo o analítica.
10. **¿Qué responsabilidades deberían corresponder al DBA, al responsable de privacidad, al área jurídica y al propietario de los datos?**
    **DBA**: Ejecución de controles técnicos. **Privacidad/Jurídico**: Procedencia legal y retención. **Propietario de datos**: Decisión de negocio sobre acceso y aprovechamiento de la información.
