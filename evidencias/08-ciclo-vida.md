# Actividad 8: Derecho de cancelación y ciclo de vida

**¿Por qué eliminar un registro de una tabla no necesariamente significa que toda la información relacionada con esa persona haya desaparecido de la organización?**

Eliminar un registro mediante `DELETE` en la tabla principal `clientes` no suprime la información presente en esquemas secundarios. Para garantizar una cancelación real, se deben contemplar: copias en respaldos (backups) históricos, bases de datos de entornos de prueba o desarrollo, registros de logs/auditoría, y archivos exportados a sistemas externos. El ciclo de vida concluye únicamente cuando la eliminación impacta todos los sistemas interconectados.

# Actividad 9: Derecho de Oposición

1. **Qué información podría necesitar mantenerse:**
   Debe mantenerse la información requerida por obligaciones legales (como facturas y RFC para el SAT) y la esencial para proveer el servicio en curso.
2. **Qué información podría dejar de utilizarse para determinada finalidad:**
   Información orientada exclusivamente a la finalidad secundaria rechazada (ej. perfiles para promociones o minería de datos).
3. **Qué mecanismos técnicos podrían separar finalidades:**
   Uso de banderas lógicas (`opt_out = true`) excluyendo los registros de vistas de marketing, o separación de datos en tablas independientes y uso de esquemas.
4. **Por qué la decisión final no debe ser tomada únicamente por el DBA:**
   Porque la validación de procedencia del derecho de oposición exige evaluar factores del marco jurídico, contratos vigentes e impacto regulatorio, competencias exclusivas de áreas legales o de cumplimiento.