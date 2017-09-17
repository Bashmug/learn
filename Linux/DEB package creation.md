# DEB package creation

### requirements

- dpkg 

### Method

1.Create a directory to build your packages in. Create a directory structure for making multiple packages under "deb" (or whatever).

```bash
mkdir deb
```

2.Create the directory structure in deb that represents where you want the script to be placed

```shell
mkdir -p ./deb/usr/local/bin
```

3.Copy the script into your new directory

```shell
cp /path/to/my/script/myscript.sh ./deb/usr/local/bin/
```

4.Make a subdirectory called "DEBIAN", this will host the package control file.

```shell
mkdir -p ./deb/DEBIAN
```

5.Create a control file.

```shell
touch ./deb/DEBIAN/control
```

6.Open the control file and enter the text below.

```
Package: myPackagename (no spaces or underscores allowed)
Priority: optional
Section: misc
Maintainer: Maintainer Name
Architecture: all
Version: 1.0 Depends: package1, package2, .........
Description: short description here long description here (don't remove space at the beginning of line) (replace this with an empty line)
```

7.Change ownership

```shell
Change ownership: sudo chown -R root:root ./deb
```

8.Create the debian package.

```shell
dpkg -b ./deb /my/output/destination/packagename.deb
```

  

 ##### For more information [link](https://wiki.ubuntu.com/PackagingGuide/Complete)

