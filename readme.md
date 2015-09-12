**¿Qué comando utilizaste en el paso 11? ¿Por qué?**
git reset --hard HEAD~1
Utilizo la opción reset HEAD~1 para deshacer la última operación con ale alrgumento --hard para perder los cambios

**- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**
git reflog

'''
b85b09b HEAD@{0}: reset: moving to HEAD~1
aaa95d5 HEAD@{1}: commit: Modyfico el fichero poem.md
b85b09b HEAD@{2}: checkout: moving from master to htmlify
b85b09b HEAD@{3}: commit (initial): Añado poem.md al repositorio
'''
git reset --hard aaa95d5

Utilizo reflog para ver los movimientos hechos en working copya
Y luego rehago el ultimo commit con cambio de working copy (opcja --hard)
utlizo SHA aaa95d5 ya que es la última operacion antes del reset.

**- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**
git merge master

No causó ningún conflicto, por que rama master no tuvo ningun nuevo commit y rama htmlify incluye todos commits que tiene master.

**- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué? **
git checkout master
git merege htmlify

No causó ningun problema. Tuvimos el marge fast-forward.


**- ¿Qué comando o comandos utilizaste en el paso 25?**
git log --graph

**- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué? **
git merge --no-ff title


Si podría hacer fast forward, todos los commits de master incluía también title. 
Lo que significa que no perderíamos ningún commit de master cambiando el puntero al mismo sitio que actualmente apunta title.

**-- ¿Qué comando o comandos utilizaste en el paso 27?**

git reflog

'''
32481ad HEAD@{0}: merge title: Merge made by the 'recursive' strategy.
525e506 HEAD@{1}: checkout: moving from title to master
6ac7f98 HEAD@{2}: checkout: moving from master to title
525e506 HEAD@{3}: checkout: moving from title to master
6ac7f98 HEAD@{4}: commit: Añado titulo al poem.md
'''

git reset 525e506


**- ¿Qué comando o comandos utilizaste en el paso 28?**

git checkout — poem.md

**- ¿Qué comando o comandos utilizaste en el paso 29?**

git branch -D title

**- ¿Qué comando o comandos utilizaste en el paso 30? **
git reflog

'''
525e506 HEAD@{0}: reset: moving to 525e506
32481ad HEAD@{1}: merge title: Merge made by the 'recursive' strategy.
525e506 HEAD@{2}: checkout: moving from title to master
6ac7f98 HEAD@{3}: checkout: moving from master to title
'''

git reset --hard 32481ad

**- ¿Qué comando o comandos usaste en el paso 32?**

git log

'''
commit 3810b4074649ba3581dabfdb6a015f251fc61d7e
Author: Izabela Holota <iza.holota@gmail.com>
Date:   Sat Sep 12 16:55:58 2015 +0200

    Modifico poem.md en la rama matrix

commit aaa95d55a8b3866d087ae9822d3bbe1420c3f1ac
Author: Izabela Holota <iza.holota@gmail.com>
Date:   Sat Sep 12 16:39:21 2015 +0200

    Modyfico el fichero poem.md

commit b85b09b12b6a5a55de4d2672f198d3f6937fe041
Author: Izabela Holota <iza.holota@gmail.com>
Date:   Sat Sep 12 16:37:08 2015 +0200

    Añado poem.md al repositorio
'''

git checkout b85b09b12b6a5a55de4d2672f198d3f6937fe041


**- ¿Qué comando o comandos usaste en el punto 33?**

git reflog

'''
b85b09b HEAD@{0}: checkout: moving from master to b85b09b12b6a5a55de4d2672f198d3f6937fe041
32481ad HEAD@{1}: reset: moving to 32481ad
525e506 HEAD@{2}: reset: moving to 525e506
32481ad HEAD@{3}: merge title: Merge made by the 'recursive' strategy.
525e506 HEAD@{4}: checkout: moving from title to master
6ac7f98 HEAD@{5}: checkout: moving from master to title
525e506 HEAD@{6}: checkout: moving from title to master
6ac7f98 HEAD@{7}: commit: Añado titulo al poem.md
'''

git checkout 32481ad


