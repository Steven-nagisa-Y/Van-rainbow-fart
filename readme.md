## rainbow-fart-template

一个简单入门级的配置文件生成脚本，可帮助有语音包但烦于配置的人快速使用。

### 使用

#### 快速上手方式
下载已经包含大量关键词的配置文件 `manifest.json` 与生成脚本 `gener.py`。

先将 `manifest.json` 内的 `name` 等字段简单填写（只是自己使用可不填写）

脚本使用：
1. 将 `gener.py` 以及 `manifest.json` 放在同一目录下，运行脚本即可快速添加所有语音条目到配置文件中：
    
    ```bash
        # 添加脚本当前目录所有语音至配置文件
        python gener.py
        # 添加指定目录所有语音至配置文件
        python gener.py [folderPath]
    ```
2. 下次有新增或删除语音时，只需指定该语音包目录即可更新该目录下的 `manifest.json` ：
    
    ```bash
        python gener.py folderPath -u
    ```

添加完成后将所有语音与 `manifest.json` 放至同一目录下打包为 `.zip` 使用网页加载该语音包即可。

如果觉得打包麻烦，可以直接将含语音和配置文件的文件夹拷贝至该插件的语音包目录，下次只需要增删文件夹内的语音即可，之后使用 `gener.py` 快速更新 `manifest.json`。

#### 纯净 DIY 方式
下载最简洁的纯净版配置 `pure/manifest.json` ，之后根据 [官方说明](https://saekiraku.github.io/vscode-rainbow-fart/#/zh/voice-packages.md) 进行 DIY 

### 自定义

之后可以根据自己需要，更改配置文件内的提示关键词和语音条目。

注：为防止乱码，语音文件名不要使用中文。

### 其他功能

针对插件包内 `manifest.json` 中的所有关键词，将其去重并生成三种格式以便更好的触发识别：
```js
    "var" -> ["var", "var ", " var "]
```
命令：
```bash
    python gener.py folderPath -k
```