# [Task 7] Common APIs used by Malware
Malware authors heavily rely on Windows APIs to accomplish their goals. It's important to know the Windows APIs used in different malware variants. It's an important step in advanced static analysis to examine the `import` functions, which can reveal much about the malware.

# Keylogger

Malware can use several Windows APIs for keylogging, including:

- **SetWindowsHookEx:** This function installs an application-defined hook procedure into a hook chain. Malware can use this function to monitor and intercept system events, such as keystrokes or mouse clicks. SetWindowsHookEx
- **GetAsyncKeyState:** This function retrieves the status of a virtual key when the function is called. Malware can use this function to determine if a key is being pressed or released. GetAsyncKeyState
- **GetKeyboardState:** This function retrieves the status of all virtual keys. Malware can use this function to determine the status of all keys on the keyboard. GetKeyboardState
- **GetKeyNameText:** This function retrieves the name of a key. Malware can use this function to determine the name of the pressed key. GetKeyNameText
Using these APIs, malware can intercept and record keystrokes, allowing it to capture sensitive information such as passwords and credit card numbers.

# Downloader

A downloader is a type of malware designed to download other malware onto a victim's system. Downloaders can be disguised as legitimate software or files and spread through malicious email attachments, software downloads, or by exploiting vulnerabilities in software. Downloaders can use various Windows APIs to perform their malicious actions. Some of the APIs commonly used by downloaders include:

- **URLDownloadToFile**: This function downloads a file from the internet and saves it to a local file. Malware can use this function to download additional malicious code or updates to the malware. URLDownloadToFile
- **WinHttpOpen:** This function initializes the WinHTTP API. Malware can use this function to establish an HTTP connection to a remote server and download additional malicious code. WinHttpOpen
- **WinHttpConnect:** This function establishes a connection to a remote server using the WinHTTP API. Malware can use this function to connect to a remote server and download additional malicious code. WinHttpConnect
- **WinHttpOpenRequest:** This function opens HTTP request using the WinHTTP API. Malware can use this function to send HTTP requests to a remote server and download additional malicious code or steal data. WinHttpOpenRequest

# C2 Communication

Command and Control (C2) communication is a method malware uses to communicate with a remote server or attacker. This communication can be used to receive commands from the attacker, send stolen data to the attacker, or download additional malware onto the victim's system.

InternetOpen: This function initializes a session for connecting to the internet. Malware can use this function to connect to a remote server and communicate with a command-and-control (C2) server. InternetOpen
InternetOpenUrl: This function opens a URL for download. Malware can use this function to download additional malicious code or steal data from a C2 server. InternetOpenUrl
HttpOpenRequest: This function opens HTTP request. Malware can use this function to send HTTP requests to a C2 server and receive commands or additional malicious code. HttpOpenRequest
HttpSendRequest: This function sends HTTP request to a C2 server. Malware can use this function to send data or receive commands from a C2 server. HttpSendRequest
Data Exfiltration

Data exfiltration is the unauthorized data transfer from an organization to an external destination. Malware can use various Windows APIs to perform data exfiltration, including:

InternetReadFile: This function reads data from a handle to an open internet resource. Malware can use this function to steal data from a compromised system and transmit it to a C2 server. InternetReadFile
FtpPutFile: This function uploads a file to an FTP server. Malware can use this function to exfiltrate stolen data to a remote server. FtpPutFile
CreateFile: This function creates or opens a file or device. Malware can use this function to read or modify files containing sensitive information or system configuration data. CreateFile
WriteFile: This function writes data to a file or device. Malware can use this function to write stolen data to a file and then exfiltrate it to a remote server. WriteFile API
GetClipboardData: This API is used to retrieve data from the clipboard. Malware can use this API to retrieve sensitive data that is copied to the clipboard. GetClipboardData
Dropper

A dropper is a malware designed to install other malware onto a victim's system. Droppers can be disguised as legitimate software or files and spread through malicious email attachments, software downloads, or by exploiting vulnerabilities in software.

CreateProcess: This function creates a new process and its primary thread. Malware can use this function to execute its code in the context of a legitimate process, making it more difficult to detect and analyze. CreateProcess
VirtualAlloc: This function reserves or commits a region of memory within the virtual address space of the calling process. Malware can use this function to allocate memory to store its code. VirtualAlloc
WriteProcessMemory: This function writes data to an area of memory within the address space of a specified process. Malware can use this function to write its code to the allocated memory. WriteProcessMemory
API Hooking

API hooking is a method malware uses to intercept calls to Windows APIs and modify their behavior. This allows the malware to avoid detection by security software and perform malicious actions such as stealing data or modifying system settings. Malware can use various APIs for hooking, including:

GetProcAddress: This function retrieves the address of an exported function or variable from a specified dynamic-link library (DLL). Malware can use this function to locate and hook API calls made by other processes. GetProcAddress
LoadLibrary: This function loads a dynamic-link library (DLL) into a process's address space. Malware can use this function to load and execute additional code from a DLL or other module. LoadLibrary
SetWindowsHookEx API: This API is used to install a hook procedure that monitors messages sent to a window or system event. Malware can use this API to intercept calls to other Windows APIs and modify their behavior. SetWindowsHookEx API
Anti-debugging and VM detection

Anti-debugging and VM detection are techniques used by malware to evade detection and analysis by security researchers. Here are some common Windows APIs used for these purposes:

IsDebuggerPresent: This function checks whether a process is running under a debugger. Malware can use this function to determine whether it is being analyzed and take appropriate action to evade detection. IsDebuggerPresent
CheckRemoteDebuggerPresent: This function checks whether a remote debugger is debugging a process. Malware can use this function to determine whether it is being analyzed and take appropriate action to evade detection. CheckRemoteDebuggerPresent
NtQueryInformationProcess: This function retrieves information about a specified process. Malware can use this function to determine whether the process is being debugged and take appropriate action to evade detection. NtQueryInformationProcess
GetTickCount: This function retrieves the number of milliseconds that have elapsed since the system was started. Malware can use this function to determine whether it is running in a virtualized environment, which may indicate that it is being analyzed. GetTickCount
GetModuleHandle: This function retrieves a handle to a specified module. Malware can use this function to determine whether it is running under a virtualized environment, which may indicate that it is being analyzed. GetModuleHandle
GetSystemMetrics: This function retrieves various system metrics and configuration settings. Malware can use this function to determine whether it is running under a virtualized environment, which may indicate that it is being analyzed. GetSystemMetrics
Details on Anti-debugging / AV detection are discussed in this room Anti-Reverse Engineering.









---
# Reference
- [THM - Advanced Static Analysis](https://tryhackme.com/r/room/advancedstaticanalysis)