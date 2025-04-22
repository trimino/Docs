# Node Window Manager Installation

## Windows Installation

1. Install Python 3.x and it to the `PATH`
	* Install via Microsoft Store
2. Install Microsoft Visual Studio >= 2017 Build Tools
	 ```powershell
	winget install -e --id Microsoft.VisualStudio.2022.BuildTools `
		--accept-package-agreements `
		--accept-source-agreements 
	```
	If the following command does not work then type the following to determine the latest package
	```powershell
	winget source update
	winget search buildtools
	```
	And use the latest id and replace it with the first command

3. Add `msvs_version=2022` to npm config
	```powershell
	npm config edit
	```
4. Add a python dependency
	```powershell
	python3 -m pip install setuptools
	```
	Keep in mind that this step is only needed when you see `ModuleNotFoundError: No module named 'distutils'`. Run this command to fix it

5. Install Node Window Manager
	```powershell
	npm i node-window-manager
	```
7. Rebuild Electron App
	```powershell
	npx electron-rebuild -f -w node-window-manager
	```
	So wtf is happening here. `electron-rebuild` relinks freshly built binaries against the same Electron headers you ship with the app. Which prevents the `invalid ELF headers` or `bad ABI` crashes at runtime


### Additional Info On Windows Installation
1. Open `Visual Studio Installer`
2. Click `Modify` ➡️ `Desktop development with C++`
3. Look at the `Optional` packages
4. Your `System Information`, specifically your `Version` (Build Version) needs to match one of the `Windows 11 SDKs`. For example my version is the following 
	> Version		10.0.26100 Build 26100
	
	So I need to install the `Windows 11 SDK (10.0.26100.0)` which can be found under the `Optional` dependencies


# Mac Installation
1. Install `HomeBrew` (makes life easier)
2. Install Python and Setup Tools
	```bash
	brew install python
	brew install python-setuptools
	```
3. Like Windows where it is alot easier to install `Visual Studio` just install `Xcode`
4. After installation of Xcode 
