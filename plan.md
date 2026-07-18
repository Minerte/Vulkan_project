we need:

# libs:
GLM GLFW

*should exist in /usr/sbin/ or /lib/*

# apps:
```
sudo apt install vulkan-tools libvulkan-dev vulkan-validationlayers spriv-tools
```

```
sudo apt install libglfw3-dev libglm-dev libxxf86vm-dev libxi-dev
```

# Folder structure:
```
Vulkan Project
├── assets
├── bin
├── shaders
├── Vulkan_validation_layer # Watch a video how to do it, but if ubuntu package it should work without having it in the project folder.
└── src
```

cmake file, To be determind later
For now use make file from the tutorial:

# Make sure to create this in src folder for now.
```
CFLAGS = -std=c++20 -O3
LDFLAGS = -lglfw -lvulkan -ldl -lpthread -lX11 -lXxf86vm -lXrandr -lXi #lX* is for x11 and not wayland 

VulkanTest: main.cpp
	g++ $(CFLAGS) -o VulkanTest main.cpp $(LDFLAGS)

.PHONY: test clean

test: VulkanTest
	./VulkanTest

clean:
	rm -f VulkanTest

```

GOOD to know linux commands:

ls -a #or ls
mkdir {Hello,hi,there,you,are} #to great multiple parent dir
find #command read doc
touch #to create file

tmux nice terminal app
