# Using Vanat

## Project Setup

To start using Vanat in your project, all you need to do is create a vanat.json file. This file will have the dependency settings for your project. It can be considered as a search list for Vanat; It will only download the packages (dependencies) for your project that are mentioned in this file.
Below is a basic skeleton of vanat.json, the file in which the dependencies will be described, then the same will be clarified.

```json
{
    "name":"Project name",
    "description": "Brief description of what the application proposes to do", 
    "require":{
        "vala":"0.36.*"
    }
}
```

The `name` is the name of your application. This marking is optional but recommended.

The `description` is a brief description of what your application proposes to do. Also optional.

The `require` is basically the key of everything and the only obligatory markup. In it you make clear what are the dependencies of your application. In this case if the vala version is below 0.36 then an error message will be thrown when installing the dependencies informing you that it is not possible to proceed because not all requirements are satisfied.

As you can see above this is the skeleton of a very basic application, with no advanced settings and no indication of any third party library.

### Okay, but what now?

Now that you already have the vanat skeleton configured in your application we will include some packages. Vanat uses as its repository the `VPackagist` where any developer can create their own packages and make them available to the community similar to github. `VPackagist` can provide you with several packages.

### A small example
For teaching purposes I will show here the use of a library for vdk created by Robert San. In the section where you define the requirements (require) in the `vanat.json` file simply add just below the line that defines that the vala needs the desired package name and version. In this case the package is `vala-development-kit/vdk` and the version is `0.1.*`. With this the new structure of `vanat.json` is:

```json
{
    "name":"Project name",
    "description": "Brief description of what the application proposes to do", 
    "require":{
        "vala":"0.36.*"
        "vala-development-kit/vdk":"0.1.*"
    }
}
```

Vanat works with a package repository, `VPackagist` (the official destination for packages created for Vanat). This is where you find the name and version of the packages you can use in your project. Then it is assumed that the `vala-development-kit/vdk` package is registered in `VPackagist`.


### All ready

Okay, now it's all ready for you to see the vanat in action. In the root folder of your application (which is the same as `vanat.json` is) run the `vanat install` command. This command will make the vanat read the settings set in the json file and install all the libraries/packages needed for your application and also these same libraries that have dependencies will have the same ones solved. Think of vanat more or less like Linux debian apt-get. In it, when installing any package, all its dependencies are resolved automatically.

Note that in the folder where your application is now there is the `vendor` folder, a vanat file (which was already there) and a `vanat.lock` file - which is the file that was automatically generated after the installation was successful.


## Installing a library directly

If you decide to install a package without having to edit the `vanat.json` file, simply notify the vanat of your choice so that it can add it to your project. To do this, type the following command on the terminal:

```shell
$ vanat require vala-development-kit/vdk
```

## Package Names

The package name consists of a `vendor` name and the project's name. Often these will be identical - the vendor name just exists to prevent naming clashes. For example, it would allow two different people to create a library named json. One might be named `igorw/json` while the other might be `seldaek/json`.

