## 🏡 Al iniciar un repo desde local
- `git init` → Empieza el control de versiones en este directorio, es como si inicializase el repositorio
- `git config --global init.defaultBranch main` → Le decimos que cuando hagamos init, la rama que se cree por defecto que se llame main en vez de master

## 📈 Comandos básicos
- `git clone urlHTTPS` → Clona un repositorio existente de GitHub en tu repositorio remoto
- `git clone urlHTTPS .` → Clona un repositorio Git desde la URL especificada y lo coloca en el directorio actual (representado por el punto "."). Al especificar el punto "." al final, le decimos a Git que clone el repositorio en la carpeta actual en lugar de crear una nueva con el nombre del repositorio. Hay que tener cuidado con esto porque la carpeta donde ejecutemos este comando tiene que estar vacía o si no nos dará este tipo de error: **fatal: destination path '.' already exists and is not an empty directory.**
- `git help [comando]` → Da información resumida sobre comandos de Git lo cual se utiliza como una guía de ayuda. Si pones "git help commit", se va a abrir una ventana en el navegador con un Manual Page con información sobre "git commit"
### git add
- `git add nombreArchivo` → Agrega ese archivo al staging area de Git
- `git add .` → Agrega todos los archivos modificados al área de preparación (staging area) de Git
- `git add *.extensiónArchivos` → Añade al stage todos los archivos con una extensión en específico, por ejemplo "git add *.html"
- `git add nombreCarpeta/` → Agrega al stage todos los archivos que están en esa carpeta
- `git add nombreCarpeta/*.extensiónArchivos` → Añade al stage todos los archivos con una extensión en específico que estén en esa carpeta, por ejemplo "git add js/*.js" añade todos los archivos .js que estén en la carpeta "js"
- `git add -A` → Añade los archivos modificados en el directorio de trabajo al staging area. E igual que `git add .` pero incluye también los archivos que se han eliminado del directorio de trabajo. Es una manera abreviada de escribir `git add --all`. Ten cuidado porque `git add -a` no existe, es con "A" mayúscula. (Es más fácil usar `git add .`)
- `git add -u` → Solo añade al stage archivos modificados y eliminados, pero no los nuevos archivos no rastreados (untracked). Es lo mismo que usar `git add update`. (Es más fácil usar `git add .`)

### git reset (Se puede hacer lo mismo que con un add, es como su opuesto)
- `git reset nombreArchivo` → Elimina del staging area ese archivo si no ha sido commiteado
- `git reset .` → Borra todos los archivos modificados al área de preparación (staging area) de Git
- `git reset *.extensiónArchivos` → Elimina al stage todos los archivos con una extensión en específico, por ejemplo "git reset *.html"
- `git reset nombreCarpeta/` → Borra al stage todos los archivos que están en esa carpeta
- `git reset nombreCarpeta/*.extensiónArchivos` → Elimina al stage todos los archivos con una extensión en específico que estén en esa carpeta, por ejemplo "git reset js/*.js" elimina todos los archivos .js que estén en la carpeta "js"
### git commit
- `git commit -m "Mensaje"` →  Crea un nuevo commit con los cambios que se encuentran en el staging area. El mensaje (-m "Mensaje") es una descripción breve de los cambios que se incluyen en el commit
- `git commit -am "Mensaje"` → Hace un git add y un git commit a la vez gracias al "-a" que es la abreviatura de "--all". Al poner el "-a" hacemos lo mismo que un `git add .`. La "m" es la abreviatura del mensaje que también utilizábamos en el anterior comando.
- `git commit --amend` → Abre en la terminal información sobre el último commit y se puede cambiar el mensaje de este. Pero es mucho más sencillo hacerlo de la siguiente manera:
- `git commit --amend -m "Nuevo Mensaje"` → Cambia el mensaje del último commit que has hecho por el nuevo mensaje
- `git commit --amend --no-edit` → Es un comando perfecto para arreglar errores en los commits. Si en un commit nos falta añadir algún archivo importante, podemos hacer un `git add nombreArchivo` para poner el archivo en el stage, y luego utilizar el comando `git commit --amend --no-edit` para modificar el último commit y añadir ese archivo. "--no-edit" indica que no se debe abrir el editor de texto para modificar el mensaje del commit existente. En otras palabras, mantiene el mensaje de commit tal como está y solo modifica el contenido del commit.

> [!NOTE]
> Para saber más sobre los commits, qué es un hash, qué significa HEAD y demás, puedes consultar el archivo [[Commits]]
 
