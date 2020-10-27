Windows DPAPI-NG lab in Python 3
=================
Forked from https://github.com/dfirfpi/dpapilab
 with every single file edited and several additions

Here I want to put some ongoing works that involve 
Windows DPAPI (Data Protection API). 
It's a lab, so something could not work: 
please see "How to Use" and ask questions.

How to install
--------------
``pip3 install wheel pytz pycryptodome python-registry construct==2.5.5-reupload``

The construct package is only needed for creddec.py & vaultdec.py (but not for ngcvaultdec.py)
pycryptodome (just like pycrypto) on Windows requires a C compiler:
Get the Build Tools at 
https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019 
and install "C++ build tools", "Windows 10 SDK" and "MSVC v142 x64/x86 build tools"

How to use
----------

Every utility has usually a minimal description that should help its usage.
Please consider that this is a *laboratory*, so don't expect that everything
will work: there are experiments and messy stuffs here. Usually I create a
brief description (as the followings) for those utilities that are completed.

In any case feel free to open a bug or a request. Any contribution is much 
appreciated.

The dpapick dependency has been added a (required) subfolder,
this is forked from https://github.com/mis-team/dpapick, 
but, again, every file changed to accomodate for using Python3.

**blobinfo.py**: this small utility simply tries to parse a DPAPI BLOB file.

**blobdec.py**: this utility tries to decrypt a *system* or *user* DPAPI BLOB
file provided, using DPAPI system key stored in LSA secrets or user password/hash.

**blobdec-with-masterkey.py**: this utility tries to decrypt a DPAPI BLOB when a 
already unlocked MasterKey (hex format) and optionally entropy.

**mkinfo.py**: this small utility simply tries to parse a MasterKey file or a
directory containing MasterKey files.

**mksdec.py**: this utility tries to decrypt the *system* MasterKey
files provided, using DPAPI system key stored in LSA secrets.

**mkudec.py**: this utility tries to unlock (decrypt) the *user* MasterKey 
files provided, using the user password or password hash.

**winwifidec.py**: this utility (formerly called wiffy.py) decrypts Windows 
WiFi password, which are (usually) system wide. To decrypt them you need: the 
DPAPI system key, which is one of the OS LSA secrets; the system MasterKeys, 
stored in  ``\Windows\System32\Microsoft\Protect\S-1-5-18\User``; the WiFi
directory, ``\ProgramData\Microsoft\WwanSvc\Profiles``.

**chrome-edge-dec.py**: this utility tries to decrypt both Cookies and 
stored browser passwords from either Chrome or the newer MS Edge browser. 

**creddec.py**: this utility tries to decrypt Windows Credential files

**crypokeysdec.py**: this utility tries to decrypt Windows Crypto files

**vaultdec.py**: this utility tries to decrypt Windows Vault files

The NGC files are accompanied by an article, later more ...

Licensing and Copyright
-----------------------

Copyright 2015 Francesco "dfirfpi" Picasso. All Rights Reserved.
Copyright 2020 Tijl "Photubias" Deneut. All Rights Reserved.

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA
02111-1307, USA.

Bugs and Support
----------------

There is no support provided with this software. There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR
PURPOSE.

For any bug or enhancement please use this site facilities.