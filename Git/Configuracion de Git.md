 
## ⚙️ Comandos de configuración
### ⚠️ Obligatorios para cualquier persona

- `git config --global user.name "Nombre Apellido"` → Configura tu nombre de usuario para Git. El nombre que configures aquí se asociará con todos los commits que hagas desde tu repositorio local
- `git config --global user.email email@email.com` → Configura tu dirección de correo electrónico para Git.

### Optativos
- `git config core.autocrlf true` → Configura la conversión automática de los caracteres de retorno de carro (CR) y salto de línea (LF) al trabajar con archivos de texto en Git. Cuando "core.autocrlf" está configurado como true, Git automáticamente convertirá los finales de línea en los archivos de texto al formato adecuado para el sistema operativo en el que estás trabajando. 

- `git config --global help.autocorrect 1` → Habilita la corrección automática en Git para sugerir comandos correctos si el comando ingresado tiene una coincidencia cercana. El valor "1" habilita esta función. 

### Comandos más avanzados de configuración
- `git config credential.helper store`→ Almacenar de forma permanente las credenciales de autenticación para un servidor remoto en el disco duro local en texto plano. Cuando configuras Git con "credential.helper store", Git recordará tu nombre de usuario y contraseña para un servidor remoto y las guardará en un archivo de texto en tu sistema. Esto evita que Git solicite tus credenciales cada vez que realizas una operación que requiere autenticación, como un push o un pull. Esto guarda tus credenciales **sin encriptar** en tu disco, por eso es mejor utilizar el comando que aparece a continuación.
- `git config --global credential.helper cache` → Guarda tus credenciales por defecto durante 15 minutos, y es la forma segura de trabajar con ellas
- `git config --global credential.helper 'cache --timeout=1800'` → Almacena las contraseñas durante 1800 segundos, es decir, 30 minutos.

### Ver configuración
- `git config --global -e` → Te muestra el archivo de configuración global
- `git config --list` → Enseña todas las configuraciones de Git.
- `git config --global user.ParametroQueremosSaber` → Enseña el parámetro por defecto que has almacenado en la configuración global. Ej; "git config --global user.email" te devuelve el email que has guardado

### Cambiar configuración
- `git config --global --replace-all user.name "Nombre Apellido"` → Establece o actualiza el nombre de usuario global.
- `git config --global --replace-all user.email email@email.com` → Establece o actualiza el correo electrónico global.
#### Eliminar alguna configuracion
- `git config --global --unset core.editor`→Elimina la configuracion en global con la parte del comando que dice --unset.

##### Configuraciones mas especificas en [[GitConfig]]