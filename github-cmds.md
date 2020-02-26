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
	
	Here `$gitname` and `$gitpass` is environment variables


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMTUxMDA5OTMsLTEzMTUxMDA5OTMsOT
czNDE4MTQ2LDU0MzM2NDc5OF19
-->