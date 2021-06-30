### Python in VSCode 非常慢

- 对比 `Pycharm` 速度是3倍的差距。
- 仔细分析后 F5 运行 python 是进入了 `debug console`，所以导致速度极低。
- 右键菜单  --  `在终端中运行python文件`
- 有大佬说如果使用了anaconda，终端运行时会自动激活conda环境，导致运行的很慢。

关闭方法：在 `setting.json` 中添加 `"python.terminal.activateEnvironment": false`

|       类型       |  速度  |
| :--------------: | :----: |
|     pycharm      | 163.53 |
|  vscode(debug)   | 293.22 |
| vscode(terminal) | 167.46 |
|  vscode(nocoda)  | 165.56 |

> 关不关conda影响好像不大，但是我觉得开着没必要所以就关了。