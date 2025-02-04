---
layout: spell
date: 17-01-2025
---

There's an issue with not being able to find references for exported modules beyond the current file via right-click > Find All References. By default, Visual Studio Code requires further configuration to support this feature.

[Github Issue discussion](https://github.com/microsoft/vscode/issues/67962#issuecomment-481034244)\\
[Visual Studio documentation](https://code.visualstudio.com/docs/nodejs/working-with-javascript#_javascript-projects-jsconfigjson)

```json
// jsconfig.json file in root folder
{
  "compilerOptions": {
    "target": "es6"
  },
  "exclude": ["node_modules"]
}
```

Furthermore, debugging for javascript can happen within the Code IDE in conjunction with the web browser. To set up debugging in Code, run the node js development server, add breakpoints in Code, then go to Run > Start Debugging which will open the application in the web browser. It's then possible to use the breakpoint controls, debugging console and watcher tools within the Code IDE. Breakpoints related to source code are better handled in the IDE, whereas breakpoints related to web browser client features are solely handled in the web browser.

A config file should emerge from this debugging set up:

```json
// $PROJECT_ROOT/.vscode/launch.json file
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "chrome",
      "request": "launch",
      "name": "Launch Chrome against localhost",
      "url": "http://localhost:8080",
      "webRoot": "${workspaceFolder}"
    }
  ]
}
```
