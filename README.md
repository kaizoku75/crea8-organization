

## Free RDP Windows 10

it's all free, don't be stingy ⭐️ yes: D

### HOW TO CREATE Windows 10 RDP
```
> Press the Fork button to create RDP (For Android / HP Users, Please Use Desktop Mode).

> visit https://dashboard.ngrok.com to get NGROK_AUTH_TOKEN

> Inside this Repo Go to Settings> Secrets> New repository secret

> Fill in the Name: Enter NGROK_AUTH_TOKEN

> Fill in Value: Visit https://dashboard.ngrok.com/auth/your-authtoken Copy and Paste in the value

> Press Add secret 

> Go To .github> workflows> blank.yml

> blank.yml will look like this:-

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
name: Crea8 Organization

on: workflow_dispatch

jobs:
  build:

    runs-on: windows-latest
    timeout-minutes: 9999

    steps:
    - name: Download Ngrok.
      run: |
        Invoke-WebRequest https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-windows-amd64.zip -OutFile ngrok.zip
        Invoke-WebRequest https://raw.githubusercontent.com/Bro-Teach/rdp/master/start.bat -OutFile start.bat
        Invoke-WebRequest https://raw.githubusercontent.com/Bro-Teach/rdp/master/wallpaper.png -OutFile wallpaper.png
        Invoke-WebRequest https://raw.githubusercontent.com/Bro-Teach/rdp/master/wallpaper.bat -OutFile wallpaper.bat
        Invoke-WebRequest https://raw.githubusercontent.com/Bro-Teach/rdp/master/loop.bat -OutFile loop.bat
    - name: Download Launcher.
      run: |
        Invoke-WebRequest https://raw.githubusercontent.com/Bro-Teach/rdp/master/launcher/Node.js.lnk -OutFile Node.js.lnk
        Invoke-WebRequest https://raw.githubusercontent.com/Bro-Teach/rdp/master/launcher/Visual%20Studio%202019.lnk -OutFile "Visual Studio 2019.lnk"
    - name: Extracting Ngrok File.
      run: Expand-Archive ngrok.zip
    - name: Connect To Account Ngrok.
      run: .\ngrok\ngrok.exe authtoken $Env:NGROK_AUTH_TOKEN
      env:
        NGROK_AUTH_TOKEN: ${{ secrets.NGROK_AUTH_TOKEN }}
    - name: Turn on Access RDP.
      run: | 
        Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server'-name "fDenyTSConnections" -Value 0
        Enable-NetFirewallRule -DisplayGroup "Remote Desktop"
        Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp' -name "UserAuthentication" -Value 1
        copy wallpaper.png D:\a\wallpaper.png
        copy wallpaper.bat D:\a\wallpaper.bat
        copy Node.js.lnk C:\Users\Public\Desktop\Node.js.lnk
        copy "Visual Studio 2019.lnk" "C:\Users\Public\Desktop\Visual Studio 2019.lnk"
    - name: Make Tunnel.
      run: Start-Process Powershell -ArgumentList '-Noexit -Command ".\ngrok\ngrok.exe tcp --region ap 3389"'
    - name: Connect To Your RDP CPU 2 Core - 7GB Ram - 256 SSD.
      run: cmd /c start.bat
    - name: Successfully Created! You Can Close Tabs Now.
      run: cmd /c loop.bat
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

> In blank.yml go to Line 9 and change 9999 minutes to "follow details given below and write minutes here"
     Details:-          
              If You Are A Kid:-
                1 Hour - 60 Min
                2 Hours - 120 Min
                3 hours - 180 Min
              
              If You Are A Teen:-
                1 Hour - 60 Min
                2 Hours - 120 Min
                3 hours - 180 Min
                4 Hours- 240 Min
                5 Hours - 300 Min
                
              If You Are A Adult:- 
                1 Hour - 60 Min
                2 Hours - 120 Min
                3 hours - 180 Min
                4 Hours - 240 Min
                5 Hours - 300 Min
                6 Hours - 360 Min
                7 Hours - 420 Min
                8 Hours - 480 Min
                
              If You Need For Business Purposes:-
                1 Hour - 60 Min
                2 Hours - 120 Min
                3 hours - 180 Min
                4 Hours - 240 Min
                5 Hours - 300 Min
                6 Hours - 360 Min
                7 Hours - 420 Min
                8 Hours - 480 Min
                9 Hours - 540 Min
                10 Hours - 600 Min
                11 Hours - 1200 Min
                12 hours - 1800 Min
                13 Hours - 2400 Min
                14 Hours - 3000 Min
                15 Hours - 3600 Min
                16 Hours - 4200 Min
                17 Hours - 4800 Min
                18 Hours - 5400 Min
                19 Hours - 6000 Min
                20 Hours - 6600 Min
                21 Hours - 7200 Min
                22 Hours - 7800 Min
                23 Hours - 8400 Min
                24 Hours - 9000 Min
              
              If You Need For Enterprise Purposes:-
                6 Months - 262800 Min 
                1 Year - 525600 Min
                5 Years - 2628000 Min
                10 Years - 5256000 min
                
> Then Save It By Commiting It
              
> Go to Action> CI> Run workflow

> Refresh Web and go to CI> build

> Press Down facing arrow button "RDP INFO LOGIN" To Get Address, User, Password.
