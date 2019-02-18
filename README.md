# GIT Course
 **Project: “Cloud Computing in European schools” <br>
 Number: Project: 2017-1-ES01-KA202-038471
**
<br><br>

#### Disclaimer
&nbsp;&nbsp;&nbsp;  *"The European Commission support for the production of this publication does not constitute an endorsement of the contents which reflects the views only of the authors, and the Commission cannot be held responsible for any use which may be made of the information contained therein."*

<br> <br> 



### Objective
&nbsp;&nbsp;&nbsp;The version control systems are an essential tool for software development, and any project that requires a collaborative work and with the possibility of having versions. This activity will allow knowing the most used version control system nowadays, GIT, and its integration in a remote repository, Github for the development of Java projects (or any other technology). Github offers us a repository on the Cloud and we will integrate it with our IDE; for this we will use Eclipse in its desktop version, or Eclipse Che in the cloud.
<br>
<br> 

### Exercise no. 1: Learning GIT

&nbsp;&nbsp;&nbsp;**Read** the [bibliography 1](https://reviblog.net/2018/03/29/tutorial-de-git-aprende-git-y-github-gitlab-de-manera-facil-rapida-y-sencilla-parte-1/) to the basics about the use of GIT. The **tutorial** is structured in 6 pages which explain the next sections:

 1. What is GIT?
 2. Installating GIT.
 3. First steps: user configuration and local repository.
 4. GIT commands
 5. Branchs.
 6. Remote repository. Github
    * README
    * Update remote repository from local repository.
    * Update local repository from remote repository
    * Copy of repositories and pull requests to original repository.
<br>    

&nbsp;&nbsp;&nbsp;After reading the tutorial, you must have done these **practices**:
 

 1. **Install** GIT.<br>
 > Windows: Download GitBash  <br>
 > Linux:  git install git <br>
  
 2. **Configure your user** for working with your local/remote repository.  <br>


>  git config --global user.name "nombre_usuario"   <br>
 > git config --global user.email "email_usuario" <br>
  
 3. **Create a local repository** called "**proyectoGIT**".  <br> 


>  mkdir proyectoGIT  <br>
>  cd proyectoGIT   <br>
>  git init  <br>
 
 4. **Practise GIT commands** : init, add (files and folders), status, commit, log, checkout id_commit, help, diff, reset --soft/hard id_commit
>   <br>
 5. Configure documents and documents type not to be managed by GIT: **.gitignore**   <br>
 >   <br>
 6. Create a **new branch** called "**branch2**". List branches, switch branch branch2, add documents to  branch2 and merge into **master branch**. <br>
 > git branch branch2 <br>
 > git checkout branch2  <br>
 > git branch  <br>
 > git checkout master  <br>
 > git merge branch2  <br>
 7. Make a snapshot to your repository by naming it with a **tag**; called "**version1.0**"
>  git tag version_1.0
  <br>
 
 8.  Create a **Github account**.
  <br>
 9.  ** Create a remote repository** in Github and called it **ProyectoGIT**.
  <br>
 10. Import your local repository, ProyectoGIT, to the remote repository, ProyectoGIT: <br>
 > git remote add origin https://github.com/YOUR_ACCOUNT/ProyectoGIT.git
 > git push -u origin master
  <br>
 11. Modify the file **README.md** withs one information  (for example create an index about "Agencia de vuelos" project). Do these changes by editing directly the file in github.
  <br>
 12. Delete your local repository and make a **clone** from your remote repository. *Have you recovered the deleted local repository?* <br>
> git clone https://github.com/YOUR_ACCOUNT/ProyectoGIT.git <br>
 13.  Modify a document in your local repository and update it in the remote repository <br>
 > git push -u origin master <br>
  14. Modify the same document but in the remote repository. After doing it, actualiza el repositorio local <br>
  > git pull

<br>
<br>
<br>
### Step no. 2: 





### Bibliography
 1. [Tutorial de Git – Aprende Git y GitHub/GitLab de manera fácil, rápida y sencilla](https://reviblog.net/2018/03/29/tutorial-de-git-aprende-git-y-github-gitlab-de-manera-facil-rapida-y-sencilla-parte-1/)




 


