# Installation

## System Requirements

The Vana has a few system requirements.You will need to make sure your desktop meets the following requirements:

  * vala (>=0.36)
  * meson (>=0.40)
  * git
  * gio-2.0
  * gee-0.8
  * gobject-2.0
  * json-glib-1.0
  
Make the clone of the repository and then go to the folder.

## Installing Vanat

Make the clone of the repository and then go to the folder.

```shell
$ git clone https://github.com/vanat/vanat.git
$ cd vanat
```

Run meson build to configure the build environment. Change to the build directory and run ninja test to build and run automated tests

```shell
$ meson build --prefix=/usr
$ cd build
$ ninja 
```

To install, use ninja install, then execute with valet

```shell
$ sudo ninja install
$ vanat
```

To verify that Vanat has been properly installed, type in the terminal:

```shell
$ vanat -v
```

If the output is correctly installed, the output should be:

```shell
vanat version 0.1.0
```
