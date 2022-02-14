* `git branch -v` Gives branches with latest commits on them

    ```
    (feature/Story-37926) $ git branch -v
    * feature/Story-12345 7f2861e Story-12345 Adding jsx model
      master            453933a Merge pull request #10 PLATFORM/java8 from feature/Story-12300 to master
    ```
    
    
* Changing branch name 
   1. Change branch name locally: 

        ```
        C:/MyWorkingDir/upadhyyo/Repository/java8:(myBranch) $ git branch --show
        myBranch
        C:/MyWorkingDir/upadhyyo/Repository/java8:(myBranch) $ git branch --move myBranch yourBranch
        C:/MyWorkingDir/upadhyyo/Repository/java8:(yourBranch) $ git branch --show
        yourBranch
        C:/MyWorkingDir/upadhyyo/Repository/java8:(yourBranch) $ 
        ```

   2. Now push changed branch name to remote
        `git push --set-upstream origin corrected-branch-name`
        For Example
        ```
        git push --set-upstream origin yourBranch
        ```
   3.  **This will push only new branch to remote, old branch is still present there, now delete it manually if you want by** 
        ```
        git push origin --delete <old branch name>
        ```
   
   
* Show all branches `git branch --all`
