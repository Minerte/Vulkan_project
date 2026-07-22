# Vulkan_project

### Dependencies:

***Debian/Ubuntu***
```
sudo add-apt-repository universe
sudo apt update
sudo apt install vulkan-tools libvulkan-dev vulkan-validationlayers libglfw3-dev libglm-dev glslang-tools shaderc

# X11
sudo apt install libxxf86vm-dev
```
***Arch Linux***
```
sudo pacman -S vulkan-tools vulkan-loader vulkan-validation-layer glfw glm glslang shaderc

# X11
sudo pacman -S libxxf86vm
```
***Gentoo Linux***
```
sudo emerge --ask media-libs/vulkan-loader media-libs/vulkan-layers dev-util/vulkan-headers dev-util/vulkan-tools dev-util/glslang media-libs/glm media-libs/glfw 

# X11
x11-libs/libXxf86vm
```
### Build

To start the Build project you need g++ or clang. After those are installed you can run these commands from the parent project folder 

```
cmake -B build
cmake --build build
# Read plan.md for more options of commands
```

and to execute the program after compile:

```
./build/Vulkan_project
# Vulkan_project variable can be change in CMakeLists.txt
```