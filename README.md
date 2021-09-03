# README #

This repository is to be used as a template for a new Ubie application. The new Ubie application should not be updated with this new application.

### How do I get set up? ###

When you start with a fresh Ubuntu installation, four steps should be completed:

* Install git by running the following command: ```sudo apt-get install git```
* clone this repository by running the following: ```git clone https://github.com/Kbij/ubieapptemplate.git```
* Enter the git repository: ```cd ubieapptemplate```
* Setup your Ubuntu environment by running (as root): ```sudo ./setup/setup_ubuntu```
* Once all required software is installed, run: ```./setup/ubie_bootstrap```


### Other scripts available ###

* ./setup/bootstrap: Setup the build environment 
* ./setup/ubie_bootstrap: Setup the build environment, and creating a new application
* ./setup/setup_ubuntu: Installing all required applications in a new Ubuntu PC
* ./setup/ubie_add_app: Run this script when you want to add a new application (recommendation is to have only a single Ubie App per repository)


### Setup git ###

Remove the reference to this "Template" repository, by running the following:
```shell
git remote remove origin
```

Then add a new remote repository by running the following:
```shell
git remote add origin yourRemoteUrl
git push -u origin master
```

### Building and running application ###

The build environment is completely setup by running the bootstrap script (see above).
Move into the correct folder (x86 or arm): cd build/Debug-x86, and run "make"

Your new application can be found in the following directory: bin/Debug-x86

### Unit testing ###

A Unit test project, with some unit test examples can be found in the <App Name\>Test folder.

### Visual Studio Code ###

Your Ubuntu installation contains a copy of Visual Studio Code. Start Code by running: ```code```, and open the Workspace "ubie.code-workspace" file.
When you open de workspace for the first time:

* Click "Yes" when code asks if you trust this folder
* Install the recommended extensions
* Select "GCC 4.8.5 x86_64-linux-gnu" as Kit


When all extensions are installed, then press "CTRL + Shift + P", and select "CMake: Configure" -> this will setup the build targets in Code

### Further reading ###

More documentation regarding Ubie application development can be found here:  ./ubiesdk/Documentation/html/index.html
You can open this in chrome via: ```google-chrome ./ubiesdk/Documentation/html/index.html```

### Directory structure ###
```bash
.
├── bin  
│   ├── Debug-arm: Debug binaries arm  
│   ├── Debug-x86: Debug binaries x86
│   ├── Release-arm: Release binaries arm
│   └── Release-x86: Release binaries x86
├── build
│   ├── Debug-arm: Build folder Debug-arm
│   ├── Debug-x86: Build folder Debug-x86
│   ├── Release-arm:Build folder Release-arm
│   └── Release-x86:Build folder Release-x86
├── setup: Various setup scripts (see above)
├── sysroot: required libraries to link
│   ├── sysroot-arm
│   └── sysroot-x86
├── Test
│   └── src: Source for the Test application
├── TestLib
│   ├── export
│   └── src: Source for your library
├── TestTest
│   └── src: Unit tests
└── ubiesdk
    ├── Documentation: Sdk docoumentation
    ├── Ubie: Ubie includes and libraries
    └── UbieSimulator: Ubie Simulator
```



