# libs:
GLM GLFW

# Folder structure:
```
Vulkan Project
├── CMakeLists.txt
├── assets
├── shaders
├── build
├── include
└── src
```

# Timeline

Week 34 see if we are done with [Vulkan tutorial](https://docs.vulkan.org/tutorial/latest/00_Introduction.html) \
If not, try to finish it before week 36.

After maybe try shaders and compute.

Then group up and see what we can build.

# Commands
tmux nice terminal app \
GOOD to know linux commands:
```
ls                                          # list
ls -a                                       # list all in dir 
cp /Sorce /Destination                      # Copy
mv /Sorce /Destination                      # Move or can be use to rename files
tree                                        # shows folder like tree branch. if installed
mkdir                                       # Creates direcoty
mkdir {Hi,how,are,you}                      # Creates sub directory
touch                                       # Creates files
find ./Vulkan_prject -name main.cpp         # find object in dir
```

CMake commands:
```
cmake -B build                              # Build
cmake -B build -DCMAKE_BUILD_TYPE=Debug     # Debug release tree
cmake -B build -DCMAKE_BUILD_TYPE=Release   # Main release tree

cmake --build build                         # Making execution file
cmake --build build --parallel              # Muliple core compile
```