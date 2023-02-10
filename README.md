# AltServer-Windows on VS 2019
In order to compile AltServer on VS 2019/2022 there a few things required.
Install the installer plugin that match your VS version from [here](https://marketplace.visualstudio.com/items?itemName=VisualStudioClient.MicrosoftVisualStudio2017InstallerProjects).

Then:
1. Clone the repository **recursively** and checkout the develop branch
2. Install [VCPKG](https://github.com/microsoft/vcpkg) to your VS.
3. Install the following packages (it takes reaaaaaally long): `vcpkg install openssl cpprestsdk[default-features,websockets] dirent mdnsresponder`
4. In the folder `(root)\Dependencies\libmobiledevice-vs` run `get-source` to download the source code
5. Download [WinSparkle](https://github.com/vslavik/winsparkle) binaries; you will need to copy the `Release` folder into `(root)\Dependencies\WinSparkle\`

The code should now compile, download the certificate, sign and install.
TODO: fix the installer project by placing the files in the proper folder.
