 

# OS - Manjaro - KDE Issues



## Firefox Screen Tearing in Manjaro

```
about:config
layers.acceleration.force-enabled = true
```

source: [*reddit*](https://www.reddit.com/r/archlinux/comments/8w8jxi/video_tearing_in_firefox_only/)

## Nvidia X Configuration File Saving Issue

When you run `nvidia-settings` to create your X configuration - no need to use root. Just run the application using the menu launcher.

When you have adjusted your settings select the **Save to X Configuration File** from the tab **X Server Display Configuration** and when prompted for a file name - use your home e.g.

```bash
~/xorg.conf
```

Depending on your use case you will either copy the file to `/etc/X11/xorg.conf.d/20-nvidia.conf` or you may want to replace the mhwd generated file in `/etc/X11/mhwd.d/nvidia.conf` e.g.

```bash
$ sudo cp xorg.conf /etc/X11/xorg.conf.d/20-nvidia.conf
```

source: [*manjaro forum*](https://forum.manjaro.org/t/root-tip-nvidia-settings-on-manjaro/33743)

## Installing MongoDB

1. install the following package from AUR
   1. install `mongodb-bin x.x.x-x`
   2. install `mongodb-tools-bin x.x.x-x`
   3. install `robo3t-bin x.x.x-x`

2. command to run the server

    ```bash
    mongod --port 27017 --dbpath /home/{USERNAME}/{DIR_NAME}
    mongod --port 27017 --dbpath /home/ashikshezan/mdb
    ```

3. to run mongo shell

   ```bash
   mongo
   ```

4. Robo 3T can also be run from the application to manage database 



## Using Multiple GitHub Account & Multiple SSH key paring

The process id to generate 2 pair of ssh key. Then add it to the 2 github account then. Then manage the working key with `ssh-agent` 

1. Create the primary ssh-key for the personal GitHub account

   ```bash
   ssh-keygen -t rsa -C "email"
   ```

2. Create another ssk-for the second organization github account.

   ```bash
   ssh-keygen -t rsa -C "email" -f "ANY_NAME"
   ```

    It will be created in the home directory so for get all the ssh key in the same place move the key pair to the `~/.ssh/` directory.

3. Adding the new SSH key to the corresponding GitHub account

4. Run the `ssh-agent` 

   ```bash
   eval `ssh-agent -s`
   or
   eval "$(ssh-agent -s)"
   ```

5. Some `ssh-agent` command

   To see all the added key 

   ```bash
   ssh-add -l
   ```

   To remove all the added key

   ```bash
   ssh-add -D
   ```

   To add the key pair you want to use to work with remote GitHub repo

   ```bash
   ssh-add ~/.ssh/KEY_NAME
   ```

   Always add the privet key to the `ssh-add` command. Never add the `.pub` public key in the local machine with `ssh-add` command. `.pub` is added in the remote host machine in this case in the website of GitHub account. 

   **So this way you have to manually add and remove the key to the ssh-agent one key at a time to connect its corresponding remote machine**

   