
# Install Node.js & ReactJS on Linux Mint 19.3 Cinnamon


### Step-1
Enable the NodeSource repository by running the following **curl**

    curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

The command will add the NodeSource signing key to your system, create an apt sources repository file, install all necessary packages and refresh the apt cache.

If you need to install another version, for example 12.x, just change  `setup_12.x`  with  `setup_13.x`

### Step-2
Once the NodeSource repository is enabled, install Node.js and npm by typing:

	sudo apt install nodejs

The nodejs package contains both the `node` and `npm` binaries.

### Step-3
Verify that the Node.js and npm were successfully installed by printing their versions:

	node --version
	npm --version

### Step-4
Install development tools to build native add-ons with the command below: 

	sudo apt-get install gcc g++ make

### Step-4
Install package manager ***yarn***

	curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
	echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
	sudo apt-get update && sudo apt-get install yarn

### Install ReactJS
Don't need to run `!=sudo npm install -g create-react-app` for globally install create-react-app

Always make a new directory and start a react with the latest version by running the command:
	
	npx create-react-app app_name


### ##Issues

1. npm update check failed

		
		sudo chown -R $USER:$(id -gn $USER) /home/sagar/.config

<!--stackedit_data:
eyJoaXN0b3J5IjpbODIyMzk5NjA1LDE3NzU1MzYyMDMsLTMyMT
E1NzUzMCwtMTAxNjUzOTcxMCwxNjUzODMwMzMsLTEzMTkwNzU4
NDgsLTE3NjM2OTE4NTJdfQ==
-->