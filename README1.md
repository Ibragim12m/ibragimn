name: Windows - Iperius Remote

on:
  workflow_dispatch:

jobs:
  build:
    name: Start Building...
    runs-on: windows-latest
    timeout-minutes: 99999
    
    steps:
      - name: Downloading & Installing Essentials
        run: |
          Invoke-WebRequest -Uri "https://raw.githubusercontent.com/ItsChanGat/Iperius-Windows-Github-RDP/refs/heads/main/down.bat" -OutFile "Downloads.bat"
          cmd /c Downloads.bat

      - name: Connect to Iperius Remote
        run: cmd /c show.bat

      - name: Time Counter
        run: cmd /c loop.bat