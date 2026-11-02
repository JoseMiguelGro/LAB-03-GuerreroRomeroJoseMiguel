# Actividad 12: Privacidad por diseño

1. **¿Qué problemas identificas?**
   Captación excesiva de datos extremadamente sensibles (salario, estado civil) no alineados a un fin justificado de registro comercial.
2. **¿Qué principio de privacidad se está ignorando?**
   Se ignora la "Privacidad por diseño", el cual exige planificar sistemas limitando la recolección desde su concepción, así como el principio de "Minimización".
3. **¿Qué preguntas realizarías antes de aprobar el diseño?**
   ¿Para qué proceso de negocio son indispensables el salario y la ocupación? ¿Están declarados explícitamente en el aviso de privacidad?
4. **¿Qué datos eliminarías?**
   `salario`, `estado_civil`, `ocupacion`, y `fecha_nacimiento` si esta última no es requerida legalmente.
5. **¿Qué datos requerirían una justificación adicional?**
   `direccion` y `codigo_postal` (deberían solicitarse únicamente si el usuario confirma un envío físico, no por defecto).
6. **¿Cómo aplicarías privacidad por defecto?**
   Ocultar o anular los campos opcionales desde el nivel de esquema de la base (`NULL` por defecto), restringiendo los `SELECT *` y delegando permisos cerrados inicialmente.

# Actividad 13: Diferenciar controles técnicos y administrativos

* **Crear roles de PostgreSQL:** Técnico (implementación directa en el motor).
* **Política de retención:** Administrativo (reglas de negocio y tiempos de vida).
* **Cifrado de datos:** Técnico (uso de algoritmos a nivel sistema).
* **Procedimiento para solicitudes ARCO:** Administrativo (proceso legal y humano).
* **Vista con información limitada:** Técnico (restricción SQL).
* **Clasificación de información:** Administrativo (etiquetado organizacional).
* **Registro de auditoría:** Técnico/Administrativo (el log del motor es técnico, pero su revisión periódica responde a políticas administrativas).
* **Política de control de acceso:** Administrativo (directriz de negocio sobre quién debe ver qué).
