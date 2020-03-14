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

	`git branch -a` - **All** branches.

	`git branch -r` - **Remote** branches only.

	`git branch -l` or `git branch` - **Local** branches only.
<!--stackedit_data:
eyJoaXN0b3J5IjpbODk2MzIwMjM2LC00NDE4MjM3NjYsLTMyOD
E5ODQzNywtMTMxNTEwMDk5MywtMTMxNTEwMDk5Myw5NzM0MTgx
NDYsNTQzMzY0Nzk4XX0=
-->