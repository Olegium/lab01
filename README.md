====ВВОД====
'''
~$ export GITHUB_USERNAME=Olegium
~$ export GIST_TOKEN=...
~$ alias ss=nano
~$ mkdir -p ${GITHUB_USERNAME}/workspace
~$ cd ${GITHUB_USERNAME}/workspace
pwd
cd
pwd
'''
====ВЫВОД====
'''
/home/oleg/Olegium/workspace
/home/oleg
'''
====ВВОД====
'''
~$ mkdir -p workspace/tasks/
~$ mkdir -p workspace/projects/
~$ mkdir -p workspace/reports/
~$ cd workspace
~/workspace$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
'''
===ВЫВОД===
'''
--2025-03-03 12:45:48-- https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
Resolving nodejs.org (nodejs.org)... 104.20.23.46, 104.20.22.46, 2606:4700:10::6814:172e, ...
Connecting to nodejs.org (nodejs.org)|104.20.23.46|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9356460 (8.9M) [application/x-xz]
Saving to: ‘node-v6.11.5-linux-x64.tar.xz

node-v6.11.5-linux-x64.ta 100%[=====================================>] 8.92M 13.3KB/s in 4m 46s

2025-03-03 12:50:36 (32.0 KB/s) - ‘node-v6.11.5-linux-x64.tar.xz’ saved [9356460/9356460]
'''
===ВВОД===
'''
~/workspace$ tar -xf node-v6.11.5-linux-x64.tar.xz
~/workspace$ rm -rf node-v6.11.5-linux-x64.tar.xz
~/workspace$ mv node-v6.11.5-linux-x64 node
~/workspace$ ls node/bin
~/workspace$ echo ${PATH}
'''
===ВЫВОД===
'''
node npm
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/lib/wsl/lib:/mnt/c/Program Files/WindowsApps/MicrosoftCorporationII.WindowsSubsystemForLinux_2.4.11.0_x64__8wekyb3d8bbwe:/mnt/c/ProgramData/Oracle/Java/javapath:/mnt/c/WINDOWS/system32:/mnt/c/WINDOWS:/mnt/c/WINDOWS/System32/Wbem:/mnt/c/WINDOWS/System32/WindowsPowerShell/v1.0/:/mnt/c/WINDOWS/System32/OpenSSH/:/mnt/c/Program Files (x86)/Windows Kits/10/Windows Performance Toolkit/:/mnt/c/Users/Oleg/AppData/Local/Microsoft/WindowsApps:/mnt/c/Users/Oleg/AppData/Roaming/Programs/Zero Install:/snap/bin
'''
===ВВОД===
'''
~/workspace$ export PATH=${PATH}:`pwd`/node/bin
~/workspace$ echo ${PATH}
'''
===ВЫВОД===
'''
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/lib/wsl/lib:/mnt/c/Program Files/WindowsApps/MicrosoftCorporationII.WindowsSubsystemForLinux_2.4.11.0_x64__8wekyb3d8bbwe:/mnt/c/ProgramData/Oracle/Java/javapath:/mnt/c/WINDOWS/system32:/mnt/c/WINDOWS:/mnt/c/WINDOWS/System32/Wbem:/mnt/c/WINDOWS/System32/WindowsPowerShell/v1.0/:/mnt/c/WINDOWS/System32/OpenSSH/:/mnt/c/Program Files (x86)/Windows Kits/10/Windows Performance Toolkit/:/mnt/c/Users/Oleg/AppData/Local/Microsoft/WindowsApps:/mnt/c/Users/Oleg/AppData/Roaming/Programs/Zero Install:/snap/bin:/home/oleg/workspace/node/bin
'''
===ВВОД===
'''
~/workspace$ mkdir -p scripts
~/workspace$ cat > scripts/activate<<EOF
> export PATH=\${PATH}:`pwd`/node/bin
> EOF
~/workspace$ source scripts/activate
~/workspace/tasks$ sudo gem install gist
~/workspace/tasks$ (umask 0077 && echo ${GIST_TOKEN} > ~/.gist)
'''
===ВЫВОД===
'''
Successfully installed gist-6.0.0
Parsing documentation for gist-6.0.0
Done installing documentation for gist after 0 seconds
1 gem installed
'''
