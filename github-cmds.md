## Some essential GitHub commands


1. Add remote origin server to a local

		git remote add origin https://github.com/ashikshezan/repo_name.git

2. Remove existing remote:

		git remote remove origin
	or
	
		git remote set-url origin New_Url_address

3. Add to git 
	
		git add -A

4. Commit to git 

		git commit -m 'add a note about the commit'

5. Push the remote called origin

		git push -u origin master
		
6. Save credential to a git repo in local machine
		
		git config credential.helper '!f() { sleep 1; echo "username=${gitname}"; echo "password=${gitpass}"; }; f'
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MjY5MjQ4MzMsOTczNDE4MTQ2LDU0Mz
M2NDc5OF19
-->