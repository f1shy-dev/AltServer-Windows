# AltServer-Windows on VS 2019

In order to compile AltServer on VS 2019 there a few things required. If you are using the Community edition of VS you will need to install the installer plugin from [here](https://marketplace.visualstudio.com/items?itemName=VisualStudioClient.MicrosoftVisualStudio2017InstallerProjects).

1. clone the repository **recursively** and checkout the `error_handling` branch
2. install and bootstrap [VCPKG](https://github.com/microsoft/vcpkg)
3. in the folder (root)\Dependencies\libmobiledevice-vs run get-source to download the source code
4. download an compile [WinSparkle](https://github.com/vslavik/winsparkle); you will need to copy the generated DLL/LIB in `(root)\Dependencies\release` (or if you only want x64, download from their github releases)
5. in the project `ldid` change the language standard from c++14 to c++17, turn off intellisense errors (misleading)
6. In the `Dependencies\libimobiledevice-vs` folder, run the `./get-source` script to download the source repos
7. In the project `imobiledevice`:
    - Open the project properties page
    - Navigate to `Configuration Properties > vcpkg`
    - Turn on `Use Vcpkg Manifest`
8. Fix the path for the icons in the RC file.
9. Copy all binaries in a single folder, including the Apple.pem file

The code should now compile, download the certificate, sign and install.
TODO: fix the installer project by placing the files in the proper folder.
