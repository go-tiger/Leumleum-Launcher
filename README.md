<p align="center"><img src="./app/assets/images/logo.png" width="150px" height="150px" alt="aventium softworks"></p>

<h1 align="center">름름 런처</h1>

<em><h5 align="center">(formerly Electron Launcher)</h5></em>


[<p align="center"><img src="https://img.shields.io/github/actions/workflow/status/go-tiger/Leumleum-Launcher/build.yml?branch=main&style=for-the-badge" alt="gh actions">](https://github.com/dscalzi/HeliosLauncher/actions) 
[<img src="https://img.shields.io/github/downloads/go-tiger/Leumleum-Launcher/total.svg?style=for-the-badge" alt="downloads">](https://github.com/go-tiger/Leumleum-Launcher/releases) 

<p align="center">Java, Forge, 또는 다른 모드를 설치하는 걱정 없이 모드 서버에 참여하세요. 그 부분은 저희가 처리해 드립니다.</p>

![Screenshot 1](https://raw.githubusercontent.com/go-tiger/Leumleum-Launcher/main/docs/1.png)
![Screenshot 2](https://raw.githubusercontent.com/go-tiger/Leumleum-Launcher/main/docs/2.png)

## 기능

* 🔒 완전한 계정 관리.
  * 여러 개의 계정을 추가하고 간편하게 전환할 수 있습니다.
  * Microsoft (OAuth 2.0) + Mojang (Yggdrasil) 인증을 완전히 지원합니다.
  * 자격 증명은 Mojang에 직접 저장 및 전송되지 않습니다.
* 📂 효율적인 에셋 관리.
  * 클라이언트 업데이트를 우리가 릴리스하는 즉시 받습니다.
  * 파일은 실행 전에 유효성을 검사합니다. 손상된 또는 잘못된 파일은 다시 다운로드됩니다.
* ☕ **자동 Java 유효성 검사.**
  * 호환되지 않는 Java 버전이 설치되어 있으면 적절한 버전을 설치해드립니다.
  * 런처를 실행하려면 Java를 설치할 필요가 없습니다.
* 📰 네이티브로 빌드된 뉴스 피드가 런처에 포함되어 있습니다.
* ⚙️ 직관적인 설정 관리, Java 제어판 포함.
* 모든 서버를 지원합니다.
  * 쉽게 서버 구성을 전환할 수 있습니다.
  * 선택한 서버의 플레이어 수를 확인할 수 있습니다.
* 자동 업데이트. 맞습니다, 런처 자체를 업데이트합니다.
*  Mojang의 서비스 상태를 확인할 수 있습니다.

이 목록은 모두를 포함하는 것은 아닙니다. 런처를 다운로드하고 설치하여 가능한 모든 기능을 확인해보세요!

#### 도움이 필요하신가요?  [위키를 확인해보세요.][wiki]

#### 프로젝트가 마음에 드셨나요? 저장소에 ⭐을 남겨주세요!

## 다운로드

GitHub 릴리스에서 다운로드할 수 있습니다. [GitHub Releases](https://github.com/go-tiger/Leumleum-Launcher/releases)

#### 최신 릴리스

[![](https://img.shields.io/github/release/go-tiger/Leumleum-Launcher.svg?style=flat-square)](https://github.com/go-tiger/Leumleum-Launcher/releases/latest)

#### 최신 사전 릴리스
[![](https://img.shields.io/github/release/go-tiger/Leumleum-Launcher/all.svg?style=flat-square)](https://github.com/go-tiger/Leumleum-Launcher/releases)

**지원되는 플랫폼**

릴리스 탭에서 시스템에 맞는 설치 파일을 선택하세요. [Releases](https://github.com/go-tiger/Leumleum-Launcher/releases)

| Platform | File |
| -------- | ---- |
| Windows x64 | `Leumleum-Launcher-setup-VERSION.exe` |
| macOS x64 | `Leumleum-Launcher-setup-VERSION-x64.dmg` |
| macOS arm64 | `Leumleum-Launcher-setup-VERSION-arm64.dmg` |
| Linux x64 | `Leumleum-Launcher-setup-VERSION.AppImage` |

## 콘솔

콘솔을 열려면 다음 단축키를 사용하세요.

```콘솔
ctrl + shift + i
```

콘솔 탭이 선택되어 있는지 확인하세요. 콘솔에 아무 것도 붙여넣지 마세요. 무엇을 할 것인지 100% 확신이 없는 경우에는 붙여넣지 마세요. 잘못 붙여넣으면 민감한 정보가 노출될 수 있습니다.

#### 출력 내용을 파일로 내보내기

콘솔 출력을 내보내려면 콘솔에서 아무 곳이나 마우스 오른쪽 버튼을 클릭한 다음 **다른 이름으로 저장**을 클릭하세요.

![console example](https://i.imgur.com/T5e73jP.png)


## Development

This section details the setup of a basic developmentment environment.

### Getting Started

**System Requirements**

* [Node.js][nodejs] v18

---

**Clone and Install Dependencies**

```console
> git clone https://github.com/dscalzi/HeliosLauncher.git
> cd HeliosLauncher
> npm install
```

---

**Launch Application**

```console
> npm start
```

---

**Build Installers**

To build for your current platform.

```console
> npm run dist
```

Build for a specific platform.

| Platform    | Command              |
| ----------- | -------------------- |
| Windows x64 | `npm run dist:win`   |
| macOS       | `npm run dist:mac`   |
| Linux x64   | `npm run dist:linux` |

Builds for macOS may not work on Windows/Linux and vice-versa.

---

### Visual Studio Code

All development of the launcher should be done using [Visual Studio Code][vscode].

Paste the following into `.vscode/launch.json`

```JSON
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Main Process",
      "type": "node",
      "request": "launch",
      "cwd": "${workspaceFolder}",
      "program": "${workspaceFolder}/node_modules/electron/cli.js",
      "args" : ["."],
      "outputCapture": "std"
    },
    {
      "name": "Debug Renderer Process",
      "type": "chrome",
      "request": "launch",
      "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron",
      "windows": {
        "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron.cmd"
      },
      "runtimeArgs": [
        "${workspaceFolder}/.",
        "--remote-debugging-port=9222"
      ],
      "webRoot": "${workspaceFolder}"
    }
  ]
}
```

This adds two debug configurations.

#### Debug Main Process

This allows you to debug Electron's [main process][mainprocess]. You can debug scripts in the [renderer process][rendererprocess] by opening the DevTools Window.

#### Debug Renderer Process

This allows you to debug Electron's [renderer process][rendererprocess]. This requires you to install the [Debugger for Chrome][chromedebugger] extension.

Note that you **cannot** open the DevTools window while using this debug configuration. Chromium only allows one debugger, opening another will crash the program.

---

### Note on Third-Party Usage

Please give credit to the original author and provide a link to the original source. This is free software, please do at least this much.

For instructions on setting up Microsoft Authentication, see https://github.com/dscalzi/HeliosLauncher/blob/master/docs/MicrosoftAuth.md.

---

## Resources

* [Wiki][wiki]
* [Nebula (Create Distribution.json)][nebula]
* [v2 Rewrite Branch (Inactive)][v2branch]

The best way to contact the developers is on Discord.

[![discord](https://discordapp.com/api/guilds/211524927831015424/embed.png?style=banner3)][discord]

---

### See you ingame.


[nodejs]: https://nodejs.org/en/ 'Node.js'
[vscode]: https://code.visualstudio.com/ 'Visual Studio Code'
[mainprocess]: https://electronjs.org/docs/tutorial/application-architecture#main-and-renderer-processes 'Main Process'
[rendererprocess]: https://electronjs.org/docs/tutorial/application-architecture#main-and-renderer-processes 'Renderer Process'
[chromedebugger]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome 'Debugger for Chrome'
[discord]: https://discord.gg/zNWUXdt 'Discord'
[wiki]: https://github.com/dscalzi/HeliosLauncher/wiki 'wiki'
[nebula]: https://github.com/dscalzi/Nebula 'dscalzi/Nebula'
[v2branch]: https://github.com/dscalzi/HeliosLauncher/tree/ts-refactor 'v2 branch'
