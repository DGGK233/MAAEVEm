# MAAEVEm
EVE手游的小助手

## 功能
- 支持多账号自动种菜和收菜

## 下载
下载地址：[MAAEVEm Releases](https://github.com/DGGK233/MAAEVEm/releases)

## 使用前配置

使用本工具前，需要对以下文件进行配置：`resource/base/pipeline/my_task.json`

### 配置步骤

1. **修改点击行星采集任务**
   ```json
   "点击行星采集": {
     "recognition": "TemplateMatch",
     "template": "行星采集图标.png",
     "action": "Click",
     "times_limit": 7,
     "is_sub": true,
     "post_delay": 5000,
     "runout_next": [ "进入仓库" ],
     "next": [ "点击行星" ]
   }
   ```
   将 `times_limit` 的值修改为账号的总数（例如，如果有7个账号，则设置为 `7`）。

2. **配置选择角色任务**
   ```json
   "选择角色": {
     "recognition": "OCR",
     "expected": [],
     "action": "Click",
     "target_offset": [ 0, 100, 0, 0 ],
     "timeout": 3000,
     "post_delay": 13000,
     "timeout_next": [ "进入游戏" ],
     "next": [ "点击行星采集" ]
   },
   "选择角色1": {
     "recognition": "OCR",
     "expected": [],
     "action": "Click",
     "target_offset": [ 0, 100, 0, 0 ],
     "timeout": 3000,
     "post_delay": 12000,
     "timeout_next": [ "进入游戏1" ],
     "next": []
   }
   ```
   在 `expected` 项中填入角色的名字或军团的名字，例如：
   ```json
   "expected": [ "EF0", "OW", "张三", "蓝色太平洋大鸟" ]
   ```

3. **配置收菜船只**
   ```json
   "点击货船": {
     "recognition": "OCR",
     "expected": "伊米卡斯",
     "action": "Click",
     "post_delay": 1000,
     "next": [ "点击激活" ]
   }
   ```
   将 `expected` 的值改为你用于收菜的船只名称。

## 说明
- 每个账号仅操作一个角色。
- 收菜的账号为最先登录的账号，收菜舰船应放置在该账号的仓库内。

---

<!-- markdownlint-disable MD033 MD041 -->
<p align="center">
  <img alt="LOGO" src="https://cdn.jsdelivr.net/gh/MaaAssistantArknights/design@main/logo/maa-logo_512x512.png" width="256" height="256" />
</p>

<div align="center">

# MaaPracticeBoilerplate

</div>

本仓库为 [MaaFramework](https://github.com/MaaXYZ/MaaFramework) 所提供的项目模板，开发者可基于此模板直接创建自己的 MaaXXX 项目。

> **MaaFramework** 是基于图像识别技术、运用 [MAA](https://github.com/MaaAssistantArknights/MaaAssistantArknights) 开发经验去芜存菁、完全重写的新一代自动化黑盒测试框架。
> 低代码的同时仍拥有高扩展性，旨在打造一款丰富、领先、且实用的开源库，助力开发者轻松编写出更好的黑盒测试程序，并推广普及。


## 即刻开始

- [📄入门文档](https://github.com/MaaXYZ/MaaFramework/blob/main/docs/zh_cn/1.1-%E5%BF%AB%E9%80%9F%E5%BC%80%E5%A7%8B.md)
- [🎞️视频教程](https://www.bilibili.com/video/BV1yr421E7MW)

## 如何开发

0. 使用右上角 `Use this template` - `Create a new repository` 来基于本模板创建您自己的项目。

1. 完整克隆本项目及子项目（地址请修改为您基于本模板创建的新项目地址）。

    ```bash
    git clone --recursive https://github.com/MaaXYZ/MaaPracticeBoilerplate.git
    ```

    **请注意，一定要完整克隆子项目，不要漏了 `--recursive`，也不要下载 zip 包！**

2. 下载 MaaFramework 的 [Release 包](https://github.com/MaaXYZ/MaaFramework/releases)，解压到 `deps` 文件夹中。

3. 配置资源文件。

    ```bash
    python ./configure.py
    ```

4. 按需求修改 `assets` 中的资源文件，请参考 MaaFramework 相关文档。

    - 可使用 [MaaDebugger](https://github.com/MaaXYZ/MaaDebugger) 进行调试；
    - 也可以在本地安装后测试：

        1. 执行安装脚本

            ```bash
            python ./install.py
            ```

        2. 运行 `install/MaaPiCli.exe`

5. 完成开发工作后，上传您的代码并发布版本。

    ```bash
    # 配置 git 信息（仅第一次需要，后续不用再配置）
    git config user.name "您的 GitHub 昵称"
    git config user.email "您的 GitHub 邮箱"
    
    # 提交修改
    git add .
    git commit -m "XX 新功能"
    git push origin HEAD -u
    ```

6. 发布您的版本

    需要先修改仓库设置 `Settings` - `Actions` - `General` - `Read and write permissions` - `Save`

    ```bash
    # CI 检测到 tag 会自动进行发版
    git tag v1.0.0
    git push origin v1.0.0
    ```

## 生态共建

MAA 正计划建设为一类项目，而非舟的单一软件。

若您的项目依赖于 MaaFramework，我们欢迎您将它命名为 MaaXXX, MXA, MAX 等等。当然，这是许可而不是限制，您也可以自由选择其他与 MAA 无关的名字，完全取决于您自己的想法！

同时，我们也非常欢迎在 [最佳实践列表](https://github.com/MaaXYZ/MaaFramework#%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5) 中添加上您的项目！

## 鸣谢

本项目由 **[MaaFramework](https://github.com/MaaXYZ/MaaFramework)** 强力驱动！

感谢以下开发者对本项目作出的贡献（下面链接改成你自己的项目地址）:

<a href="https://github.com/MaaXYZ/MaaFramework/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=MaaXYZ/MaaFramework&max=1000" />
</a>

