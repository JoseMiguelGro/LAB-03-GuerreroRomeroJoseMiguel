# Actividad 15: Propuesta de arquitectura de datos

## Arquitectura Conceptual por Finalidad

*   **Esquema `operacion`**: Alberga `clientes_soporte` (sin RFC, ni edad) para Atención al cliente. Acceso restringido por rol `soporte_role`.
*   **Esquema `financiero`**: Alberga datos confidenciales vinculados (RFC, domicilio fiscal). Acceso restringido a `facturacion_role`. Controles: Cifrado TDE.
*   **Esquema `analitica`**: Alberga únicamente Vistas Materializadas que transforman edades a rangos (`v_analitica_clientes`) y omiten identificadores.
*   **Esquema `auditoria`**: Almacena logs de accesos (`pg_audit`) inmutables.

## Controles Técnicos
Implementación de Row-Level Security (RLS) para segregación departamental, triggers para borrado cascada programado (`politica_retencion`), y rutinas de enmascaramiento antes de realizar dumps para desarrollo.
