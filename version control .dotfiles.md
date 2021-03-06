# Version control your `.dotfiles` file with Github Gist

## Install Gist on your machine

First of all `gist` CLI package have to be installed in your computer. It will be found on Debian and Arch linux official repos.

For Arch run the following command
~~~bash
sudo pacman -S gist 
~~~

## Log into Gist with your Github account

If you want to associate your gists with your GitHub account, you need to login
with gist. It doesn't store your username and password, it just uses them to get
an OAuth2 token (with the "gist" permission).

```bash
gist --login
Requesting login parameters...
Please sign in at https://github.com/login/device
  and enter code: ****-****
```
Enter the code and you are logged in

This token is stored in `~/.gist` and used for all future gisting. If you need to
you can revoke it from https://github.com/settings/tokens, or just delete the
file.  If you need to store tokens for both github.com and a Github Enterprise instance
you can save your Github Enterprise token in `~/.gist.github.example.com` where
"github.example.com" is the URL for your Github Enterprise instance.


‌After you've done this, you can still upload gists anonymously with `-a`.

    gist -a a.rb

[Learn more about using the gist client](https://github.com/defunkt/gist#readme).

## Create a Gist with your bashrc file

Upload your `.bashrc` file to your account as a private gist using the following command

```bash
gist -p -o -d "My .bashrc" ~/.bashrc
```

Here `-p` specifies that you want this file to be private, `-o` will open a new browser tab with the gist page as soon as it's uploaded, and `-d` is used to add a description for your file.

## Create an alias for updating your file

Open your `.bashrc` file with the editor of your choice, in this case I'll be using vscode.

```bashrc
sudo code ~/.bashrc
```

At the end of the file add the following command
```bash
#Gist Bashrc alias
alias gistbash="gist -u GIST_ID ~/.bashrc"
```

Where `GIST_ID` is the id of your uploaded gist file found in the URL.
![](https://i.gyazo.com/50511a8d248d0e55178dfe924b00a44d.png)

Save the file and close out your editor.

## Commit your changes

Either open a new terminal window or source your `.bashrc` by using the following command
```bash
source ~/.bashrc
```

Now you can run your alias every time after making a change to your `.bashrc` file to update your gist.
```bash
gistbash
```

After you run the command you should be able to see the changes reflected on the gist!
