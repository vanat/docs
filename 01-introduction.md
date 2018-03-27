# Introduction

## What is Vanat?

Vanat is a tool for dependency management in Vala. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you.

## Dependency management

Vanat is not a package manager in the same sense as Yum or Apt are. Yes, it deals with "packages" or libraries, but it manages them on a per-project basis, installing them in a directory (e.g. vendor) inside your project. It does not install anything globally.
This idea is not new and Vanat is inspired by composer and node's npm.

### Suppose:
  1. You have a project that depends on a number of libraries.
  2. Some of those libraries depend on other libraries.

### Vanat:
  1. Enables you to declare the libraries you depend on.
  2. Finds out which versions of which packages can and need to be installed, and installs them (meaning it downloads them into your project). 
  
See the Basic usage chapter for more details on declaring dependencies.



