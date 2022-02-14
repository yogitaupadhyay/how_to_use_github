## 🔶 `git push origin java8`\
   Internal working:\
   git expands name java8 to `refs/heads/java8:refs/heads/java8` or `java8:java8`, means take my java8 branch and merge it to remotes java8 branch

   You can use this this to push changes to your remote branch with a diff name for example

      git push origin java8:AdvancedJava
    
## 🔶 How not to type password everyTime you do git push

  The simplest is just to keep it in memory for a few minutes, which you can
  easily set up by running 

    git config --global credential.helper cache.

 
