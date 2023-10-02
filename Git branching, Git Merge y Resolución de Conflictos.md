# GIT BRANCH

- **Concepto Principal:** Una Branch o rama es una línea independiente de desarrollo, nos permite obtener un entorno limpio donde implementar cambios que luego se reflejarán en la línea de desarrollo principal (comúnmente la rama develop).

A la hora de ingresar en un proyecto o comenzar uno nuevo nos encontraremos con la difícil tarea de organizar este flujo de trabajo.

Normalmente se utiliza la siguiente convención para organizar el flujo de trabajo:

  - Se posee una rama histórica que es protegida y no puede ser eliminada por ambiente (develop, master, qa)
  - Por cada feature que implementemos crearemos una rama, luego de terminado el desarrollo se debe mergear la misma a su rama padre.
  - No se realizan commit directamente sobre las ramas históricas (develop, master, etc)

# GIT MERGE

- **Concepto Principal:** Git Merge es la forma en que Git reúne historias separadas que han evolucionado en paralelo, permitiendo que los cambios de diferentes ramas se unan en una sola.

- **Comando Git Merge:** Se utiliza el comando git merge para realizar fusiones. Este comando combina dos líneas de desarrollo, generalmente dos ramas, creando un nuevo "commit de fusión" que integra los cambios de ambas.

- **Commit Base:** Git encuentra un "commit base" común entre las ramas que se están fusionando. Este commit es el punto en la historia donde ambas líneas de desarrollo divergieron.

- **Tipos de Merges:** Hay dos tipos principales de fusiones: "Fast-Forward Merge" y "3-Way Merge". El primero se utiliza cuando hay un camino lineal entre las ramas y simplemente avanza una rama hacia la otra. El segundo se utiliza cuando las ramas han divergido y Git crea un nuevo commit de fusión con tres commits involucrados: las puntas de ambas ramas y su ancestro común.

- **Preparación para la fusión:** Antes de fusionar, es importante confirmar la rama receptora, actualizar las ramas con los últimos cambios remotos y asegurarse de que todo esté al día.

- **Uso de --no-ff:** La opción --no-ff permite generar un commit de fusión incluso en un "Fast-Forward Merge". Esto es útil para documentar todas las fusiones en el repositorio.

- **Usos Comunes:** Los desarrolladores suelen utilizar "Fast-Forward Merge" para características pequeñas o correcciones de errores, mientras que las "3-Way Merges" se reservan para la integración de características más complejas y de larga duración.

- **Documentación y Control de Versiones:** Git Merge es una herramienta crucial para llevar un registro de los cambios y colaborar de manera efectiva en proyectos de desarrollo de software.

# Resolución De Git Merge Conflicts

**Qué es un Git Merge Conflict:** Un conflicto en Git merge conflict es un evento que sucede cuando Git no es capaz de resolver distintas diferencias de código automáticamente entre dos commits. Git solo es capaz de hacer merge automáticamente si los commits se encuentran en diferentes líneas o ramas.

**Tipos de Conflictos:**

1. **Conflictos al empezar el merge:** Si se han realizados cambios al working directory del staging area del proyecto, el merge no se realizará. En este caso los conflictos suceden debido a cambios pendientes que deben ser resueltos. Por ejemplo, haber hecho cambios a un archivo, e intentar un git merge sin haber hecho un git commit anteriormente.
   - Mensaje de error: error: Entry '<fileName>' not uptodate. Cannot merge. (Changes in working directory).

2. **Conflictos durante el merge:** Este tipo de error indica que existen conflictos entre la rama local y la rama siendo unificada (merged). En este tipo de casos, git resuelve la mayor cantidad posible de conflictos, pero en ciertas instancias requerirá nuestra intervención en los archivos.
   - Mensaje de error: error: Entry '<fileName>' would be overwritten by merge. Cannot merge. (Changes in staging area).

**Cómo resolver un conflicto:**

1. Identificar el archivo con conflictos utilizando git merge (que fallará) y git status para información adicional.
2. Abrir el archivo conflictivo y resolver los conflictos. Estos estarán separados por una línea: “=======”.
3. Para resolver este conflicto, simplemente borramos el separador, al igual que el contenido que no agregamos al archivo (“===”, “<<<”,  etc).
4. Utilizar git add para tracker los los nuevos cambios del merge.
5. Creamos un nuevo commit utilizando git commit.
6. Git creará un nuevo merge commit para finalizar el commit.

**Comandos de Git para resolución de conflictos:**

- `git log --merge`: Muestra una lista de commits que están causando conflictos.
- `git diff`: Ayuda a identificar las diferencias entre los estados de los repositorios o conflictos.
- `git checkout`: Es utilizado para navegar a distintas ramas.
- `git reset --mixed`: Utilizado para deshacer cambios en la working directory o staging área.
- `git merge --abort`: Es utilizado para abortar el proceso de git merge y retornar al estado previo el merge.

**Referencias:**

- [Git merge conflicts: Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)
- [How to resolve merge conflicts in Git? - Simplilearn.com](https://www.simplilearn.com/tutorials/git-tutorial/merge-conflicts-in-git)
- [Git Merge | Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/using-branches/git-merge)
