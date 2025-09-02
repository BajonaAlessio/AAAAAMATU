
--------Clono il repo--------
PS C:\Users\devops3\Documents> https://github.com/BajonaAlessio/AAAAAMATU.git
Cloning into 'AAAAAMATU'...

--------controllo il git branch--------

PS C:\Users\devops3\Documents\AAAAAMATU> git branch -a
* main
  remotes/origin/develop
  remotes/origin/main
  remotes/origin/feature/modifica
  remotes/origin/feature/test

--------uso git switch per crearmi un branch locale di tutti i remoti--------

PS C:\Users\devops3\Documents\AAAAAMATU> git switch develop
branch 'develop' set up to track 'origin/develop'.

PS C:\Users\devops3\Documents\AAAAAMATU> git switch feature/modifica

PS C:\Users\devops3\Documents\AAAAAMATU> git switch feature/test

PS C:\Users\devops3\Documents\AAAAAMATU> git branch
  develop
  feature/modifica
* feature/test
  main

--------pull di tutto--------

§§ SPIEGAZIONE DI COSA FA ff only §§

git pull = git fetch + git merge

It downloads changes from the remote branch and then merges them into your local branch.

--ff-only = "fast-forward only"

It refuses to merge unless the changes can be applied as a fast-forward.

Remote:   A---B---C
Local:    A---B

git pull --ff-only will just "fast-forward" your local branch to C. No merge commits are created.

-----------
^^^^^^^^^^
PS C:\Users\devops3\Documents\AAAAAMATU> git pull --ff-only




--------crea un nuovo (sotto)branch feature/testeli e muoviti li--------

PS C:\Users\devops3\Documents\AAAAAMATU> git switch -c feature/testeli
Switched to a new branch 'feature/testeli'

-------- controlla se ora esiste --------

PS C:\Users\devops3\Documents\AAAAAMATU> git branch
  develop
  feature/modifica
  feature/test
* feature/testeli  <--------------------- CREATO
  main

-------- git add + drag and drop file per il percorso, quando voglio caricare solo un file --------

PS C:\Users\devops3\Documents\AAAAAMATU> git add c:\Users\devops3\Documents\AAAAAMATU\Readmeli.md


PS C:\Users\devops3\Documents\AAAAAMATU> git commit -m "New Readme"

-------- Dove lo pusho? Devo aggiungere dopo origin il nome del branch --------
PS C:\Users\devops3\Documents\AAAAAMATU> git push -u origin feature/testeli