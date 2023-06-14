# jetson-nano-setup
## Installing the Jetpack 

<p> Follow this tutorial to download and flash your sd card with with the JetPack 4.6.1 image. <br> Then boot up the Jetson nano and complete the initial setup.<br> The official NVIDIA tutorial: https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit  </p>

## Basic Setup

<p> Run on the terminal: <br><br> sudo apt update <br> sudo apt upgrade<br><br> and you'll see tensorrt packages kept back </p>

<p> The normal updates/install commmands don't work <br><br> So run this instead: <br><br> sudo apt --only-upgrade install tensorrt <br><br> It should now now run properly. Now run this complete this step: <br><br> sudo apt install nvidia-container-csv-tensorrt <br><br> Now this should install properly as well. </p>

## Fixing CUDA packages on the environment

<p> Normally when you flash the Jetpack you CUDA and CuDNN come preinstalled with the Jetson Nano. But for some reason their paths are broken and when trying to install frameworks like darknet that use CUDA the packages can't be found. There's a few lines of code that can help you fix this and save you a whole lot of time/effort.<br></p>
  
  
 <p> First install the nano text editor. To install run this on the Terminal:<br> <br> sudo apt install nano <br><br>  
  

  
  
