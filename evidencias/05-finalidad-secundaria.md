# Actividad 5: Analizar una finalidad secundaria

1. **¿El hecho de que la organización ya tenga los datos significa automáticamente que puede utilizarlos para cualquier finalidad?**
   No. El principio de "limitación de finalidad" estipula que los datos solo pueden usarse para los propósitos originales informados al titular.
2. **¿Qué preguntas debería realizar la organización antes de implementar este tratamiento?**
   ¿El Aviso de Privacidad permite el uso de datos para marketing? ¿Se cuenta con el consentimiento explícito del titular? ¿Es compatible esta finalidad secundaria con la obtención original?
3. **¿Qué datos serían realmente necesarios?**
   Solamente la ciudad, la edad (o su rango) y un canal de contacto (correo).
4. **¿Necesitaría el área de marketing acceso directo a clientes?**
   No. Marketing no requiere ni RFC, ni código postal, ni acceso total a la tabla, sino una vista específica o un reporte exportado.
5. **¿Qué controles técnicos podrían limitar la información entregada?**
   Vistas restringidas (Row-Level Security o segmentación de columnas), control de acceso por roles, y seudonimización de nombres.

# Actividad 6: Derechos ARCO y la base de datos (Acceso)

**Pregunta:** 
1. **¿Qué información adicional debería proporcionar la organización además del resultado de esta consulta?** Además del resultado de la base de datos, la organización debe informar las finalidades del tratamiento, la base jurídica que lo sustenta, si existen transferencias a terceros y los tiempos de retención.

# Actividad 7: Derecho de rectificación

**Preguntas:**
1. **¿Cómo podría comprobarse que el cambio fue autorizado?**
   Mediante la validación de identidad en el portal del usuario (ej. sesión iniciada, token, o código enviado al correo anterior).
2. **¿Debería registrarse quién realizó el cambio?**
   Sí, debe existir un registro de auditoría identificando qué empleado o sistema efectuó la actualización.
3. **¿Por qué la trazabilidad será importante?**
   La trazabilidad permite determinar quién modificó un dato y cuándo, lo cual es crítico frente a incidentes de seguridad o disputas de privacidad.
