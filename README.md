Well Hello there Nice to Meet You Guys today iam gonna to show you how to Make a Windows Ultimate ISO Using DISM And ANYBurn

Steps 

-Download The ISOs 

-DISM 

-ANYBURN

Requires a Hard Disk that isnt full or running out of storage or eles it will fail

Programs Needed

-Anyburn 

1ST STEP: DOWNLOAD THE ISO
BEFORE YOU EVEN BEGIN WITH THE DISM COMMANDS AND ANYBURN YOU WILL NEED A WINDOWS ISO FILE FOR THAT
Windows 11:https://www.microsoft.com/en-us/software-download/windows11

Windows 10:https://www.microsoft.com/en-us/software-download/windows10

Windows 8.1:https://archive.org/details/win-8.1-english-x-64_20211019

Windows 7:https://archive.org/details/windows-7-ultimate-x-64-sp-1-fully-updated

Windows Vista:https://archive.org/details/vistasp2_ldr_escrow.251211-1611

Windows XP Doesnt Support Install.wim Windows Longhorn Does

Step 2 : DISM Commands
Mount Your ISOs and Remember thier Drive Letter (Example G: , H: , I:)

Now the 1st command is to locate the Drive

G:/

G:/ cd Sources

G:/Sources dism /Get-ImageInfo /ImageFile:"wimpath"

"wimpath"=the Adress of Install.wim (Example :G:/Sources/install.wim)

you should see This 
Index : 1
Name : Windows 10 Home
Description : Windows 10 Home
Size : 15,139,674,619 bytes

Index : 2
Name : Windows 10 Home N
Description : Windows 10 Home N
Size : 14,368,233,902 bytes

Index : 3
Name : Windows 10 Home Single Language
Description : Windows 10 Home Single Language
Size : 15,142,346,396 bytes

Index : 4
Name : Windows 10 Education
Description : Windows 10 Education
Size : 15,475,605,732 bytes

Index : 5
Name : Windows 10 Education N
Description : Windows 10 Education N
Size : 14,684,197,328 bytes

Index : 6
Name : Windows 10 Pro
Description : Windows 10 Pro
Size : 15,472,691,215 bytes

Index : 7
Name : Windows 10 Pro N
Description : Windows 10 Pro N
Size : 14,702,310,788 bytes

Index : 8
Name : Windows 10 Pro Education
Description : Windows 10 Pro Education
Size : 15,475,544,150 bytes

Index : 9
Name : Windows 10 Pro Education N
Description : Windows 10 Pro Education N
Size : 14,684,134,846 bytes

Index : 10
Name : Windows 10 Pro for Workstations
Description : Windows 10 Pro for Workstations
Size : 15,475,574,941 bytes

Index : 11
Name : Windows 10 Pro N for Workstations
Description : Windows 10 Pro N for Workstations
Size : 14,684,166,087 bytes

Size : 14,684,166,087 bytes

if you used the iso from the Link i added you should see The same thing But Windows 8.1 Pro and Windows 8.1

Index : 1
Name : Windows 8.1 Pro
Description : Windows 8.1 Pro
Size : 13,185,962,705 bytes

Index : 2
Name : Windows 8.1
Description : Windows 8.1
Size : 13,116,079,066 bytes

now if you gonna Add Windows 7 and Vista in a Windows 10 / 11 PE Install.wim it will install windows normally but once Windows 7 Or Windows Vista Starts Booting it will BugCheck (BSOD) Witht the Stopcode:0x0000005C (0x000000000000010B ,0x0000000000000003 , 0x0000000000000000 ,0x0000000000000000)
(HAL_INITIALIZATION_FAILED)Which It means Windows failed while initializing the Hardware Abstraction Layer (HAL) very early during boot.(The Windows PE environment or boot files weren't compatible with what Setup expected) because the Win10PE is trying to boot windows 7 and vista in UEFI mode but win 7 and vista only support LegacyBoot
