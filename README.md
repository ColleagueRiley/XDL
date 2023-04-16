# XLib Dynamic Loader
A single header file that dymaically loads the Xlib and GLX library

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

