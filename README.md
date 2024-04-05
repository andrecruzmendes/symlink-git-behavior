# symlink-git-behavior

This is a simple project to test and observe the functioning of `symlinks` in `git`.

In some experiments with symbolic links, it is noted that applications often cannot distinguish between files because they access the links transparently through the file system provided by the operating system.

Would the behavior with `git` be similar to this? Not the case. `Git` was developed to manage files in a distinct and efficient manner, including symbolic links.

Support for symbolic links has been present in `git` since its early versions, designed for `Unix` systems. When a symbolic link is added to the project, `git` stores information about its path and target, reflecting the correct behavior of the file system. Then, during cloning, `git` attempts to restore the symbolic link.

## Project Details

In this project, there is a file `file.txt` and a symbolic link `symlink.txt` whose target is the file `file.txt`. You can clone this repository to experiment whether the feature is preserved locally.

### Compatibility Note

It is important to note that this feature may not be fully compatible with all scenarios, depending on the operating system. Symlinks originate from `Unix` systems. In some cases, it may be necessary to use special `git` parameters, such as `-c core.symlinks=true`.

### Windows Support

It is known that `Windows` has supported symbolic links since `Vista`, although the user still needs specific permissions, usually present in the administrator profile.
