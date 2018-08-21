# Respuestas para los ejercicios de [learngitbranching.js.org](https://learngitbranching.js.org/)
## Main

En este documento se describen soluciones a los distintos problemas. Estas soluciones no son todas óptimas de acuerdo con el simulador.

1. Secuencia introductoria

    1. Introducción a los commits de Git

        ```shell
            $ git commit
            $ git commit
        ```

    2. Brancheando [sic] en Git

        ```shell
            $ git branch bugFix
            $ git checkout bugFix
        ```

    3. Mergeando [sic] en Git

        ```shell
            $ git branch bugFix
            $ git checkout bugFix
            $ git commit
            $ git checkout master
            $ git commit
            $ git merge bugFix
        ```

    4. Introducción a rebase

        ```shell
            $ git branch bugFix
            $ git checkout bugFix
            $ git commit
            $ git checkout master
            $ git commit
            $ git checkout bugFix
            $ git rebase master
        ```

2. Acelerando

    1. Desatacheá [sic] tu HEAD

        ```shell
            $ git checkout C4
        ```

    2. Referencias relativas (^)

        ```shell
            $ git checkout bugFix
            $ git checkout HEAD^
        ```

    3. Referencias relativas #2 (~)

        ```shell
            $ git checkout bugFix
            $ git branch -f bugFix HEAD~3
            $ git branch -f master C6
            $ git checkout C1
        ```

    4. Revirtiendo cambios en git [sic]

        ```shell
            $ git reset HEAD^
            $ git checkout pushed
            $ git revert HEAD
            # Obsérvese que reset tiene como argumento al commit al que se quiere regresar, mientras que revert tiene como argumento al commit que se quiere deshacer.
        ```

3. Moviendo el trabajo por allí

    1. Introducción a cherry-pick

        ```shell
            $ git cherry-pick C3 C4 C7
        ```

    2. Introducción al rebase interactivo

        *Nota*: En la versión en español, la opción pick en la simulación está activa por defecto en todos los commits: "hacer pick" en un commit descarta el mismo. Se asume que esto sucede en esta solución.

        ```shell
            $ git rebase -i C1
            # En la ventana, hacer lo siguiente:
            #   1. Hacer pick en C2. (Descarta el commit C2.)
            #   2. Colocar los siguientes commits de arriba a abajo en la lista en el orden siguiente: C3, C5 y C4.
        ```

4. Bolsa de gatos

    1. Tomando un único commit

        ```shell
            $ git checkout master
            $ git cherry-pick C4
        ```

    2. Haciendo malabares con los commits

        ```shell
            $ git rebase -i C1
            # En la ventana, hacer lo siguiente:
            #   1. Colocar los siguientes commits de arriba a abajo en la lista en el orden siguiente: C3, C2.
            $ git commit --amend
            $ git rebase -i C1
            # En la ventana, hacer lo siguiente:
            #   1. Colocar los siguientes commits de arriba a abajo en la lista en el orden siguiente: C2'', C3'.
            $ git checkout master
            $ git merge caption
        ```

    3. Haciendo malabares con los commits #2

        ```shell
            $ git checkout master
            $ git cherry-pick C2
            $ git commit --amend
            $ git cherry-pick C3
        ```

    4. Tags en git [sic]

        ```shell
            $ git tag v0 C1
            $ git tag v1 C2
            $ git checkout v1
        ```

    5. Git Describe [sic]
        *Nota*: Para acreditar este nivel, sólo se requiere hacer un commit. Este nivel busca ilustrar el uso de `git describe`.

        ```shell
            # Por ejemplo, dentro del simulador el comando:
            $ git describe
            # devuelve:
            v1_2_gc6
            # dónde v1 es el tag más cercano en los ancestros del commit siendo descrito (C6) y 2 es la distancia a dicho tag desde el commit.
            # En este caso, como no se suministra algún argumento al comando, se utiliza el commit en el que se encuentra HEAD. (En este caso, C6.)
            $ git commit
        ```

5. Temas avanzados

    1. Rebaseando [sic] más de 9000 veces

        ```shell
            $ git checkout bugFix
            $ git rebase master
            $ git checkout side
            $ git rebase bugFix
            $ git checkout another
            $ git rebase side
            $ git checkout master
            $ git rebase another
        ```

    2. Múltiples padres

        ```shell
            $ git checkout HEAD~^2~
            # El número después de ^ elige al "segundo" padre del merge, es decir, el último commit de la rama que se usa como argumento en `git merge`.
            $ git branch bugWork
            $ git checkout master
        ```

    3. Ensalada de branches

        ```shell
            $ git checkout one
            $ git cherry-pick C4 C3 C2
            $ git checkout two
            $ git cherry-pick C5 C4 C3 C2
            $ git branch -f three C2
        ```

## Remote

1. Push & Pull [sic] -- Git [sic] Remotes!

    1. Introducción a clone

        ```shell

        ```

    2. Ramas remotas

        ```shell

        ```

    3. `git fetch`

        ```shell

        ```

    4. `git pull`

        ```shell

        ```

    5. Simulando el trabajo en equipo

        ```shell

        ```

    6. `git push`

        ```shell

        ```

    7. Historia divergente

        ```shell

        ```


2. Hasta el origin y más allá -- Git Remotes [sic] avanzado! [sic]

    1. ¡Push Master! [sic]

        ```shell

        ```

    2. Mergeando [sic] con los remotos

        ```shell

        ```

    3. Trackeando [sic] remotos

        ```shell

        ```

    4. Parámetros de `git push`

        ```shell

        ```

    5. ¡Más! [sic] Parámetros de `git push`

        ```shell

        ```

    6. Parámetros de fetch

        ```shell

        ```

    7. Origen de nada

        ```shell

        ```

    8. Parámetros de pull

        ```shell

        ```
