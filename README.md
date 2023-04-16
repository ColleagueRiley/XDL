# XLib Dynamic Loader
A single header file that dynamically loads the Xlib and GLX library

# Use
First, define XDL_IMPLEMENTATION and include the library 

```c
#define XDL_IMPLEMENTATION
#include "XDL.h"
```

Next, use XDL_init to load the X11 module 

```c
XDLModule x11Module = XDL_init();
```

When you're done, make sure to close the module, this frees all the allocated data and stored functions\
This is not required in c++ because the data should automatically deallocate. (unless you have XDL_NO_DEALLOCATE enabled)

```c
XDL_close(x11Module);
```

You can also define XDL_NO_GLX before including XDL if you don't want to include the GLX module 

```c
#define XDL_NO_GLX
#define XDL_IMPLEMENTATION
#include "XDL.h"
```

XDL_NO_DEALLOCATE can be defined to turn of automatic deallocation for c++

```cpp
#define XDL_NO_DEALLOCATE
#define XDL_IMPLEMENTATION
#include "XDL.h"
```

# Credits
* [GLFW](https://github.com/GLFW/GLFW) Much of this implementation is based on GLFW's internal x11 dynamic loader
        A great portion of the declarations for the X11 module are sourced from GLFW

* [stb](https://github.com/nothings/stb/) This project is heavily inspired by the stb single header files

# License
This project is public domain but credit  would be greatly appreciated. 