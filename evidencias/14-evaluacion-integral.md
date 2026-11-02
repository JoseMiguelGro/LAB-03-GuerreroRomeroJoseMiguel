# Actividad 14: Escenario integral

| Problema | Principio afectado | Riesgo | Control propuesto |
| :--- | :--- | :--- | :--- |
| Analítica ve tabla directa | Minimización / Confidencialidad | Fuga de datos | Crear vistas agregadas |
| Analítica accede al RFC | Limitación de finalidad | Exposición financiera | Retirar columnas ajenas |
| Retención de 12 años sin política | Conservación / Retención | Sanción legal | Implementar política de borrado |
| Copias a desarrollo con datos reales | Privacidad por diseño | Fuga en entornos débiles | Enmascaramiento y datos sintéticos |
| Marketing usa correos sin claridad | Limitación de finalidad / Consentimiento | Multas por SPAM | Añadir campo `opt_out` |
| Analítica ve edad nominal | Minimización | Identificación secundaria | Usar sentencias `CASE` |
| Sin documentación de finalidades | Gobierno de datos | Uso descontrolado | Crear catálogo de datos |
| Teléfono expuesto masivamente | Privacidad por defecto | Robo de identidad corporativa | Revocar permisos y separar en RBAC |
| Modelo monolítico para consultas | Proporcionalidad | Acceso indiscriminado | Separación lógica (esquemas) |
| No se audita quién lee qué en prod. | Trazabilidad | Exfiltración silenciosa | Configurar `pgaudit` |
