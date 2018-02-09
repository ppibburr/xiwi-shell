# xiwi-shell
Auto-start a linux chroot and integrate linux apps into chrome 

# How TO
At chromeos enviroment press Ctrl+RightArrow to enter shell  
Login as root or `sudo su` after login.  

Download and install the system tool
```
cd $HOME
curl https://raw.githubusercontent.com/ppibburr/xiwi-shell/master/system-setup > ./system-setup
chmod 755 system-setup
./system-setup
```

Return to the chromeos desktop enviroment Ctrl+LeftArrow  
Open the developer console: Ctrl+ALt+t  

Modify bashrc to to start the xiwi-launcher service automatically

```
echo "sudo enter-chroot xiwi-launcher" >> $HOME/.bashrc
```

Enter the chroot and setup chroot enviroment.  

```
sudo enter-chroot
sudo apt-get install ruby
sudo gem i sinatra

cd $HOME
curl https://raw.githubusercontent.com/ppibburr/xiwi-shell/master/chroot-setup > ./chroot-setup
chmod 755 chroot-setup
./chroot-setup

exit
exit
exit
```

Next Steps
===

Set chrome to open the developer terminal at startup.  
It will automatically enter `shell` and then `sudo enter-chroot xiwi-launcher`

You now have a launcher for linux applications at `http://0.0.0.0:4567/xiwi`  
You can bookmarkit or pin to shelf.  

Once you launch an app you can bookmark or pin the result page to the shelf, which will then launch the app.  
