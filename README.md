# jetson-nano-setup
## Installing the Jetpack 

<p> Follow this tutorial to download and flash your sd card with with the JetPack 4.6.1 image. <br> Then boot up the Jetson nano and complete the initial setup.<br> The official NVIDIA tutorial: https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit  </p>

## Basic Setup

<p> Run on the terminal: <br><br> sudo apt update <br> sudo apt upgrade<br><br> and you'll see tensorrt packages kept back </p>

<p> The normal updates/install commmands don't work <br><br> So run this instead: <br><br> sudo apt --only-upgrade install tensorrt <br><br> It should now now run properly. Now run this complete this step: <br><br> sudo apt install nvidia-container-csv-tensorrt <br><br> Now this should install properly as well. </p>

## Fixing CUDA packages on the environment

<p> Normally when you flash the Jetpack you CUDA and CuDNN come preinstalled with the Jetson Nano. But for some reason their paths are broken and when trying to install frameworks like darknet that use CUDA the packages can't be found. There's a few lines of code that can help you fix this and save you a whole lot of time/effort.<br></p>
  
  
 <p> First install the nano text editor. To install run this on the Terminal:<br> <br> sudo apt install nano </p>
 
 <p> Now update the bashrc to have the paths. Run this on the terminal: <br> <br>
  
  nano ~/.bashrc<br><br>
  
  Now in the bashrc scroll to the bottom and add these two lines:<br>
  
  export PATH=${PATH}:/usr/local/cuda/bin<br>
  export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:/usr/local/cuda/lib64<br><br>
  
  Now this should fix your issues.</p>
  
  ## Additional recommendations to be safe
  
  ### Set up jtop to monitor your jetson nano device
   
   <p> First install pip: the python package manager. The jetson nano comes with Python 3.6.9 preinstalled. So now run this on the command line: <br> <br>
  
  sudo apt install python3-pip<br></p>
  
  <p> Then install the jtop package using the installed pip3. Run this on the commandline:<br><br>
  
  sudo pip3 install -U jetson-stats<br>
  jtop<br><br>
  
  Now you can run jtop whenever you want to check the state and information of your jetson device.</p>
  
  ### Different python versions and Virtual environments
  
  <p>While implementing multiple projects at the same time on the same device they might require different versions of the same dependencies. But installing them during runtime is very cumbersome.<br><br> 
  Some projects may even require different versions of python. So for that we can install pyenv and virtualenv packages to make things easier.<br> <br> 
  Run the following commands on the command line:<br><br>
  
  sudo apt install -y build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl<br>
  curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash<br>
  echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.bashrc<br>
  echo 'eval "$(pyenv init -)"' >> ~/.bashrc<br>
  echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc<br>
  source ~/.bashrc<br><br>
  #using the following commands to install your desired python version<br>
  pyenv install 3.7.12<br>
  pyenv install 3.8.12<br>
  pyenv install 3.9.7<br><br>
  
  And now to set one version as the current version:<br> <br>
  pyenv global 3.9.7<br>
  python --version<br> <br>
  
  And thats it you're done!</p>
  
                       
  
 


  
 
  

  
  
