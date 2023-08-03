<h1 align="center">
    build2 Package for tinyobjloader
</h1>

<p align="center">
    This project builds and defines the build2 package for <a href="https://github.com/tinyobjloader/tinyobjloader">tinyobjloader</a>.
    Tiny but powerful single file wavefront obj loader written in C++03. No dependency except for C++ STL. It can parse over 10M polygons with moderate memory and time.

    `tinyobjloader` is good for embedding .obj loader to your (global illumination) renderer ;-)
</p>

<p align="center">
    <a href="https://github.com/tinyobjloader/tinyobjloader">
        <img src="https://img.shields.io/website/https/github.com/tinyobjloader/tinyobjloader.svg?down_message=offline&label=Official&style=for-the-badge&up_color=blue&up_message=online">
    </a>
    <a href="https://github.com/build2-packaging/tinyobjloader">
        <img src="https://img.shields.io/website/https/github.com/build2-packaging/tinyobjloader.svg?down_message=offline&label=build2&style=for-the-badge&up_color=blue&up_message=online">
    </a>
    <a href="https://cppget.org/libtinyobjloader">
        <img src="https://img.shields.io/website/https/cppget.org/libtinyobjloader.svg?down_message=offline&label=cppget.org&style=for-the-badge&up_color=blue&up_message=online">
    </a>
    <a href="https://queue.cppget.org/libtinyobjloader">
        <img src="https://img.shields.io/website/https/queue.cppget.org/libtinyobjloader.svg?down_message=empty&down_color=blue&label=queue.cppget.org&style=for-the-badge&up_color=orange&up_message=running">
    </a>
</p>

## Usage
Make sure to add the stable section of the `cppget.org` repository to your project's `repositories.manifest` to be able to fetch this package.

    :
    role: prerequisite
    location: https://pkg.cppget.org/1/beta
    # trust: ...

If the stable section of `cppget.org` is not an option then add this Git repository itself instead as a prerequisite.

    :
    role: prerequisite
    location: https://github.com/build2-packaging/tinyobjloader.git

Add the respective dependency in your project's `manifest` file to make the package available for import.

    depends: libtinyobjloader ^ 2.0.0-

The library can be imported by the following declaration in a `buildfile`.

    import tinyobjloader = libtinyobjloader%lib{tinyobjloader}

## Configuration
There are no configuration options vailable.

## Issues and Notes
- The shared library is not built or exported.
- Test fuzzers are not compiled and run by the package's build system.
- Exampels are not compiled and run by the package's build system.

## Contributing
Thanks in advance for your help and contribution to keep this package up-to-date.
For now, please, file an issue on [GitHub](https://github.com/build2-packaging/tinyobjloader/issues) for everything that is not described below.

### Recommend Updating Version
Please, file an issue on [GitHub](https://github.com/build2-packaging/tinyobjloader/issues) with the new recommended version.

### Update Version by Pull Request
1. Fork the repository on [GitHub](https://github.com/build2-packaging/tinyobjloader) and clone it to your local machine.
2. Run `git submodule init` and `git submodule update` to get the current upstream directory.
3. Inside the `upstream` directory, checkout the new library version `X.Y.Z` by calling `git checkout vX.Y.Z` that you want to be packaged. Here, it is probably not a version but the newest commit from the master branch instead.
4. If needed, change source files, `buildfiles`, and symbolic links accordingly to create a working build2 package. Make sure not to directly depend on the upstream directory inside the build system but use symbolic links instead.
5. Update library version in `manifest` file if it has changed or add package update by using `+n` for the `n`-th update.
6. Make an appropriate commit message by using imperative mood and a capital letter at the start and push the new commit to the `master` branch.
7. Run `bdep ci` and test for errors.
8. If everything works fine, make a pull request on GitHub and write down the `bdep ci` link to your CI tests.
9. After a successful pull request, we will run the appropriate commands to publish a new package version.

### Update Version Directly if You Have Permissions
1. Inside the `upstream` directory, checkout the new library version `X.Y.Z` by calling `git checkout vX.Y.Z` that you want to be packaged. Here, it is probably not a version but the newest commit from the master branch instead.
2. If needed, change source files, `buildfiles`, and symbolic links accordingly to create a working build2 package. Make sure not to directly depend on the upstream directory inside the build system but use symbolic links instead.
3. Update library version in `manifest` file if it has changed or add package update by using `+n` for the `n`-th update.
4. Make an appropriate commit message by using imperative mood and a capital letter at the start and push the new commit to the `master` branch.
5. Run `bdep ci` and test for errors and warnings.
6. When successful, run `bdep release --tag --push` to push new tag version to repository.
7. Run `bdep publish` to publish the package to [cppget.org](https://cppget.org).
