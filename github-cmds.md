# Some essential GitHub commands

1. #### Add remote origin server to a local
   
        git remote add origin https://github.com/ashikshezan/repo_name.git

2. #### Remove existing remote:
   
        git remote remove origin
   
    or
   
        git remote set-url origin New_Url_address

3. #### Add to git
   
        git add -A

4. #### Commit to git
   
        git commit -m 'add a note about the commit'

5. #### Push the remote called origin
   
        git push -u origin master

6. #### Save credential to a git repository in local machine
   
        git config credential.helper '!f() { sleep 1; echo "username=${gitname}"; echo "password=${gitpass}"; }; f'
   
    Here `$gitname` and `$gitpass` is environment variables. 
    For this purpose sitting up an SSH key is more convenient. 

7. #### Remote Origin information
   
        git remote show origin

8. #### List of branch
   
    **All** branches.
   
        git branch -a 
   
    **Remote** branches only
   
        git branch -r
   
    **Local** branches only
   
        git branch -l` or `git branch

9. #### Switch branches
   
   ```bash
    git checkout BRANCH_NAME 
   ```

10. #### Create branch
    
    First, you create your branch locally:
    
    ```
    git checkout -b <branch-name> # Create a new branch and check it out
    ```
    
    The remote branch is automatically created when you push it to the 
    remote server. So when you feel ready for it, you can just do:
    
    ```
    git push <remote-name> <branch-name> 
    ```
    
    Where `<remote-name>` is typically `origin`,
     the name which git gives to the remote you cloned from. Your colleagues
     would then just pull that branch, and it's automatically created 
    locally.
    
    Note however that formally, the format is:
    
    ```
    git push <remote-name> <local-branch-name>:<remote-branch-name>
    ```
    
    But when you omit one, it assumes both branch names are the same. Having said this, as a word of **caution**, do not make the critical mistake of specifying only `:<remote-branch-name>` (with the colon), or the remote branch will be deleted!
    
    So that a subsequent `git pull` will know what to do, you might instead want to use:
    
    ```
    git push --set-upstream <remote-name> <local-branch-name> 
    ```
    
    As described below, the `--set-upstream` option sets up an upstream branch:
    
    > For every branch that is up to date or
    >  successfully pushed, add upstream
    >  (tracking) reference, used by
    >  argument-less git-pull(1) and other
    >  commands.
    
    <small>*source*: <u>stackoverflow</u></small>