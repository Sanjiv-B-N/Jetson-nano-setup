# jetson-nano-setup
## Installing the Jetpack 

<p> Follow this tutorial to download and flash your sd card with with the JetPack 4.6.1 image. <br> Then boot up the Jetson nano and complete the initial setup.<br> The official NVIDIA tutorial: https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit  </p>

## Basic Setup

<p> Run on the terminal: <br> sudo apt update <br> sudo apt upgrade<br> and you'll see tensorrt packages kept back </p>

<p> The normal updates/install commmands don't work <br><br> So run this instead: <br><br> sudo apt --only-upgrade install tensorrt <br><br> It should now now run properly. Now run this complete this step: <br><br> sudo apt install nvidia-container-csv-tensorrt <br><br> Now this should install properly as well. </p>

## Fixing CUDA packages on the environment


  
  
