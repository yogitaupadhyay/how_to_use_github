* Three tree states
  1. The working directory tree
     * Git status can be used to show changes to the Working Directory. 
  2. Staging Index tree
     * This tree is tracking Working Directory changes, that have been promoted with git add, to be stored in the next commit. This tree is a complex internal caching mechanism. 
       Git generally tries to hide the implementation details of the Staging Index from the user.
     * To debug the staging indexes -
      ```
           D:\MyWorkingDir\how_to_use_github>git ls-files -s
          100644 b7f0d00b6542c9e97617459f75a526412e6fe444 0       commands.txt
          100644 6e5869ae9d6a4cc9db7e76d0b2893d3fe4dbc1ab 0       git commands
          100644 1d76f91765e6462620fff0acfd81d99540a89ffb 0       github.rtf

          D:\MyWorkingDir\how_to_use_github>git ls-files
          commands.txt
          git commands
          github.rtf

        ```
        1. -s here means staging area.
        2. The -s option displays additional metadata for the files in the Staging Index. This metadata is the `staged contents' mode bits`, `object name`, and `stage number`.
        3. Object name = standard Git object SHA-1 hash, It is a hash of the content of the files.
        4. The Commit History stores its own object SHA's for identifying pointers to commits and refs and the Staging Index has its own object SHA's for tracking versions of 
         files in the index.
  3.  Commit History
        * The git commit command adds changes to a permanent snapshot that lives in the Commit History. 
          This snapshot also includes the state of the Staging Index at the time of commit.
