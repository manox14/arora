# Introduction #

Building on Windows is complex and nuanced, and the specifics of the steps will greatly depend on your Windows and software configuration and the particular choices you make in setting up your toolchain. This outline offers instructions on building with Visual C++ and assumes that you already have a working compiler and platform SDK. See [[1](http://en.wikipedia.org/wiki/Microsoft_Windows_SDK)] and [[2](http://www.microsoft.com/downloads/details.aspx?FamilyId=E6E1C3DF-A74F-4207-8586-711EBE331CDC&displaylang=en)].


# Details #
## Step 1: OpenSSL ##
_Note: If you are using the same compiler as [Shining Light's Win32 OpenSSL Build](http://www.slproweb.com/products/Win32OpenSSL.html), you may skip this step by using the DLLs included in the installer. You should note the location to where the installer copies the applicable DLLs._

1. Download and install [ActivePerl](http://www.activestate.com/store/download.aspx?prdGUID=81fbce82-6bd5-49bc-a915-08d58c2648ca).

2. Download the [OpenSSL source](http://www.openssl.org/source/), and extract it somewhere.

3. Build from the Visual C++ command prompt:
```
openssl_source_directory> perl Configure VC-WIN32
openssl_source_directory> ms\do_masm
openssl_source_directory> nmake -f ms\ntdll.mak
```
_Note: Depending on how broken the current OpenSSL release is on Win32, you may have to edit some of the perl build files. This may include adding a few lines to strip out nasty characters, adding defines to headers, or other hackishness. Put on your thinking cap, use google, and figure out how to fix the problems that will most likely occur._
Some more hints about possible ssl building can be found here: https://wiki.secondlife.com/wiki/Qt_Webkit_Win32_Build_Instructions

## Step 2: Qt ##
1. Download the source of either the latest release of qt or the latest snapshot, and extract it somewhere.

2. Run the configure.exe script with the following options and `nmake` from the Visual C++ command prompt:
```
qt_source_directory> configure.exe -release -shared -no-exceptions -webkit -phonon -no-qt3support -no-opengl -openssl-linked -fast -I <openssl_source_directory>\include -L <openssl_source_directory>\out32dll
qt_source_directory> nmake
```
Replace `<openssl_source_directory>` with the real location.

_Note: You may experience compiler errors relating to openssl header files. Refer to the comment above about OpenSSL maybe being broken._

3. Add `<qt_source_directory>\bin` to your `PATH`.

## Step 3: Arora ##
Download and compile Arora using [this wiki's instructions](source.md) from the Visual C++ command prompt.

## Step 4: NSIS Installer ##
1. Download and install [NSIS](http://nsis.sourceforge.net/Download).

2. Download the [KillProcDLL plugin](http://nsis.sourceforge.net/KillProcDLL_plug-in) and move the appropriate DLL into the NSIS plugins directory.

3. Edit the hard-coded directory paths in `arora_source_directory\windowsinstaller.nsi` to reflect the appropriate location of the libraries installed above. Also edit the location and file for the Visual C++ redistributable package to reflect the version of Visual C++ you used to compile.

4. Compile `arora_source_directory\windowsinstaller.nsi` with the NSIS compiler by right clicking on the file and choosing "Compile NSIS Script" or by using the NSIS compiler interface directly.

5. Run the output installer file titled "Arora Snapshot (Date) Installer.exe".


# Todo #
  * Figure out a more elegant solution to include the Visual C++ Runtime without having to bundle the entire gigantic redistributable and run it silently from NSIS.
  * On Vista, have "Run Arora" box at end of the installer run it from the user's account, not the administrators account.