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


 5. Configure documents and documents type not to be managed by GIT: **.gitignore**  


 6. Create a **new branch** called "**branch2**". List branches, switch branch branch2, add documents to  branch2 and merge into **master branch**. <br>
 

> git branch branch2 <br>
>  git checkout branch2  <br>
>  git branch  <br>
>  git checkout master  <br>
>  git merge branch2  <br>
 7. Make a snapshot to your repository by naming it with a **tag**; called "**version1.0**"
> git tag version_1.0   <br>
 
 8.  Create a **Github account**.  
 


 
 9.  **Create a remote repository** in Github and called it **ProyectoGIT**.  


 10. **Import your local repository**, ProyectoGIT, to the remote repository, ProyectoGIT:  
 
>  git remote add origin https://github.com/YOUR_ACCOUNT/ProyectoGIT.git <br>
>  git push -u origin master   <br>

 11. Modify the file **README.md** withs one information  (for example create an index about "Agencia de vuelos" project). Do these changes by editing directly the file in github.  


 12. Delete your local repository and make a **clone** from your remote repository. *Have you recovered the deleted local repository?* <br>
> git clone https://github.com/YOUR_ACCOUNT/ProyectoGIT.git <br>

 13.  Modify a document in your local repository and update it in the remote repository <br>
> git push -u origin master <br>
 
  14. Modify the same document but in the remote repository. After doing it, actualiza el repositorio local <br>
  > git pull <br>


### Exercise no. 2: GIT in Eclipse
   After learning to use GIT for local and remote repositories, now it is time to integrate this technology with the Integrated Development Environment. The objective is deploy our project, our Java project for example, in a GIT repository and synchonize with a remote repository in Github in order to publish it and work in team with other developers.

   The article in the [bibliography 4](https://www.arquitecturajava.com/eclipse-git-repositorios/) explains the steps to do it.   The steps are:
   

 1. Create a Java project.
 ![Creating a Java project](/img/CreateJavaProject.png)  


 2. Create a Java Class with the typical message "Hello World".
 ![Creating a Java app](/img/CreateJavaClass.png)  


 3. Integrate the project into a GIT repository (Right botton on the project name --> Team --> Share project --> Select GIT repository location ). Note that after doing the project dissappears in the Eclipse workspace (/home/user/eclipse-workspace/ProyectoGIT and it is moved to the GIT repository folder, /home/user/repositorios-github/ProyectoGIT).  
  ![Step to integrated Java project in GIT](/img/JavaProjectinGIT.png)  
  

The final result is our project in a GIT repository:  

![The project integrated in GIT](/img/JavaProjectinGIT-2.png) 


Whe can check the new location of the Java project:
  
  ![New location for the project](/img/GitRepositoryFolder.png)


  4.Add our project to GIT ("git add") y versionar ("git commit"):  
  (/img/Eclipse-Add.png)  
    ![Project add](/img/Eclipse-Add.png)
    ![Project commit](/img/Eclipse-Commit.png)  
    




5. The GIT plugin allow to use another perspective. Open **GIT perspective**. do click on the tab 'Git Staging'.   
![Project commit](/img/Eclipse-GITPerspective.png)  

As you can see, there are serveral parts:  

  * <u>Unstaged changes</u>: files that are inside the GIT repository and they have changed. You can add the files to the stage by clicking in '+' button. This action makes a "git add"
  * <u>Staged changes</u>: files that have been add to the stage. In case you decide to follow their versions, you must do click on "Commit button".
  * <u>Commit message</u>: to describe the message for the commit (git commit -m MESSAGE)
  * <u>Commit</u>:   is the result of "git commit -m MESSAGE".
  * <u>Commit and push</u>: these button add the option to upload the changes to the remote repository.  
  


6. **Do other changes and commit them**. For example, change "Hello World" to "Bye World". Commit the change with the message "Commit 2".
![Project commit 2](/img/Eclipse-commit2.png)


  We have just realized that we need to **go back** to the initial step because we don't want the new code developed. 
![Project reset - go back -](/img/Eclipse-reset.png)


   What is the content of the file "HelloWorld.java"?  ("Hello World" again?).  Cool!  *Our Version Control System works fine!!*


7. It is the time to **upload our local repository to Github** to **share it to other developers**. 
![Project - upload GitHub-Step 1](/img/Eclipse-Push-1.png)
![Project - upload GitHub-Step 2](/img/Eclipse-Push-2.png)
![Project - upload GitHub-Step 3](/img/Eclipse-Push-3.png)
![Project - upload GitHub-Step 4](/img/Eclipse-Push-4.png)
![Project - upload GitHub-Step 5](/img/Eclipse-Push-5.png)

We can check that our local project is in the remote repository in Github.
![Project - upload GitHub-Step 6](/img/Eclipse-Push-6.png)





### Bibliography
 1. [Tutorial de Git – Aprende Git y GitHub/GitLab de manera fácil, rápida y sencilla](https://reviblog.net/2018/03/29/tutorial-de-git-aprende-git-y-github-gitlab-de-manera-facil-rapida-y-sencilla-parte-1/)
 2. [Qué es Markdown, para qué sirve y cómo usarlo](https://www.genbeta.com/guia-de-inicio/que-es-markdown-para-que-sirve-y-como-usarlo)
 3. [Sintaxis Markdown](https://markdown.es/sintaxis-markdown/#parrafos)
 4. [Eclipse Git , Repositorios locales y remotos](https://www.arquitecturajava.com/eclipse-git-repositorios/)





 


