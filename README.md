# armbian-kDs
Kubernetes on the Orange Pi Lite 1

Additional part - Vagrant build:

```
# You’ll need to install a plug-in that will enable us to resize the primary storage device. Without it, the default Vagrant images are too small to build Armbian.
vagrant plugin install vagrant-disksize
```

```
# Clone the Armbian repo project.  
git clone --depth 1 https://github.com/armbian/build

# Make the Vagrant box available. This might take a while but only needs to be done once.  
vagrant box add ubuntu/focal64

# If the box gets updated by the folks at HashiCorp, we'll want to update our copy too.  
# This only needs done once and a while.  
vagrant box update
```
```
# We have to be in the same directory as the Vagrant file, which is in the build/config/templates directory.
cd build/config/templates

#  Note that you can edit the Vagrant  file to specify the number of cpus and amount of memory you want Vagrant to use.
# And now we simply let vagrant create our box and bring it up.
vagrant up

# When the box has been installed we can get access via ssh.
# (No need for passwords, Vagrant installs the keys we'll need.)
vagrant ssh
```

# Additional:
```
# Shutdown, but leave the box around for more building at a later time:  
vagrant halt

# Trash the box and remove all the related storage devices.  
vagrant destroy
```