PDF EB Split (Creating a Portable EXE)

Enlarge the PDF to your desired scale, split it into multiple A4/A3 pages, and create a new PDF with a dotted junction guide and a label at the top left. If you print this PDF at 100% (actual size), the scale will be applied as is.

This folder is a "Portable EXE Creation Package" that requires building only once on a hospital PC. We have included the necessary installation files (wheels folder) so that you can run it even if the internet is blocked.

Contents

pdf_split_scale.py: Main program body

build_exe.bat: Build script for double-click (offline priority)

wheels\: Offline installation package (wheels) — Do not delete

README.md: This instruction manual

Instructions (3 steps)

Python Installation (First time): Python 3.10~3.13 on 64-bit Windows. When installing from https://www.python.org/downloads/, check "Add python.exe to PATH".

Alternatively, install "Python 3.12" from the Microsoft Store.

Copy the entire folder to your PC, then double-click build_exe.bat (takes a few minutes).

Once finished, dist\YonseiEBSplit.exe will be created. → Copying this single EXE will allow it to run on any PC without Python.

Usage

Double-click → File Selection GUI (Select PDF → Enter scale → Select paper size → Run)

Command Line

Enter YonseiEBSplit.exe.pdf --scale 1.75 --paper A4

Options: --paper A3 / --orientation auto|portrait|landscape / --overlap 10 / --margin 5

Print & Assembly

Print the created PDF at "Actual Size / 100%" (Do not use "Fit to Page").

Arrange the labels at the top left of each chapter in the order [Page R / Entire C / Entire]. Cut along the red dotted lines on each of the two adjacent sheets, then align the cut edges (without overlapping) and attach them. Since the dotted lines on the two sheets mark the exact center of the overlapping section—that is, the exact same location—cutting and butting them results in a perfect fit without any loss or overlap. (If you leave the dotted lines intact and overlap them, the image will disappear by the width of the overlap, so be sure to use the "cut and butt" method.)

Note

If you are using 32-bit Windows or Python is not version 3.10 or 3.13, the offline installation of wheels may not work. In that case, connect to the internet and run build_exe.bat to automatically proceed to the online installation.

To display only the GUI without a console window, add --noconsole to the end of the PyInstaller line in build_exe.bat and rebuild.

before
<img width="473" height="593" alt="image" src="https://github.com/user-attachments/assets/c1241bc1-4ead-466c-993f-9aa44a1cb6a1" />


after
<img width="703" height="721" alt="image" src="https://github.com/user-attachments/assets/d968ce65-e2b0-4fcc-9380-aa4923a10944" />

