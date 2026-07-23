# Vulkan_project

### Dependencies:

***Debian/Ubuntu***
```
sudo add-apt-repository universe
sudo apt update
sudo apt install vulkan-tools libvulkan-dev vulkan-validationlayers libglfw3-dev libglm-dev glslang-tools shaderc

sudo apt install build-essential cmake ninja-build libtinyobjloader-dev libstb-dev libtinygltf-dev nlohmann-json3-dev libxi-dev

# X11
sudo apt install libxxf86vm-dev
```
***Arch Linux***
```
sudo pacman -S vulkan-tools vulkan-loader vulkan-validation-layer glfw glm glslang shaderc

sudo pacman -S nlohmann-json base-devel cmake ninja tinyobjloader tinygltf

# X11
sudo pacman -S libxxf86vm
```
***Gentoo Linux***
```
sudo emerge --ask media-libs/vulkan-loader media-libs/vulkan-layers dev-util/vulkan-headers dev-util/vulkan-tools dev-util/glslang media-libs/glm media-libs/glfw 

sudo emerge --ask dev-cpp/nlohmann_json dev-build/cmake dev-build/ninja 

# X11
x11-libs/libXxf86vm
```

Download version linux-x86_64-1.4.350.1 [Vulkan SDK](https://vulkan.lunarg.com/sdk/home)
Then extract it.
```
mkdir Vulkan_project/vulkansdk-linux
# then
tar -xf vulkansdk-linux-x86_64-1.4.350.1.tar.xz -C Vulkan_project/vulkansdk-linux/
# then
cd Vulakn_project/vulkansdk-linux/
# then 
ln -s 1.4.350.1 default
```
now add the following to your ~/.bashrc or ~/.zshrc

```
source ~/Vulkan_project/vulkansdk-linux/default/setup-env.sh
# restart terminal or run
source ~/.bashrc
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