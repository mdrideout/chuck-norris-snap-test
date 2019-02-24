# Instructions
These instructions are for testing a nodejs snap vm that responds to HTTP requests. This code is from this snap tutorial: https://github.com/ubuntu/snap-tutorials-code/tree/master/build-a-nodejs-service/final

## Create The Snap
At the root of the project directory, run `snapcraft`. This will generate a **.snap** file that can be installed onto a multipass virtual machine.
```
snapcraft
```

## Run Snap On Multipass Linux Virtual Machine
Create a Linux virtual machine for testing snaps
```
multipass launch -n testvm
```

Copy the .snap file to the virtual machine
```
multipass copy-files *.snap testvm:
```

Connect to the virtual machine
```
multipass shell testvm
```

Install the snap inside the virtual machine
```
sudo snap install --dangerous *.snap
```


Confirm the snap is installed by listing your installed snaps
```
snap list
```

Perform a curl command inside the virtual machine - this will return HTML code
```
curl localhost
```

Exit the virtual machine
```
exit
```
