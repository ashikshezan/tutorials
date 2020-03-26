### Creating a Virtualenv in python 3

		python3 -m virtualenv 'ENV_NAME'

### Showing Directory Size

		du -hs /path/to/directory

-   `-h`  is to get the numbers "human readable", e.g. get  `140M`  instead of  `143260`  (size in KBytes)
-   `-s`  is for summary (otherwise you'll get not only the size of the folder but also for everything  _in_  the folder separately)


### Generating ssh key

	ssh-keygen -t rsa -b 4096
Then copy the `id_rsa.pub` file and  past it to the github settings.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMyODE3OTMzNCwxOTMwOTM2NzQ4LC0xND
EwNjA4MzY4LC00MDUxODk4MjksLTQwNTE4OTgyOV19
-->