# 运行文档 Operating-document

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg?style=for-the-badge)](https://creativecommons.org/licenses/by-nc-sa/4.0) ![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=Markdown&logoColor=ffffff) ![BuildStateCard](https://img.shields.io/github/actions/workflow/status/apocfly/Operating-document/ci.yml?style=for-the-badge&logo=github&label=build)  ![LastCommitCard](https://img.shields.io/github/last-commit/apocfly/Operating-document?display_timestamp=committer&style=for-the-badge&logo=github)


本项目是一个以Markdown语言以及[Zensical](https://zensical.org/)文档站(原[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)))组成的一个模拟飞行平台运营所集成的所有文档，这包括：

- 行为准则
- 管制员考核大纲
- ......



# Roadmap

您可以在我们的[github仓库项目](https://github.com/orgs/apocfly/projects/2)中，查阅我们的发展路线



# 官方讨论渠道

您可以前往我们的github仓库、[Discussions板块](https://github.com/apocfly/Operating-document/discussions)与我们一同进行讨论，请务必遵守[社区行为准则](CODE_OF_CONDUCT.md)哦



## 使用指南

- 将本仓库Fork下来，再用Github page将此项目运营在github服务器上
- 将本仓库Fork下来，和我们一起对其进行编写！
- 也可以将此项目部署在本地服务器上



## 使用Python库

### 基础库：

| Package  | Version |
| -------- | ------- |
| zensical | 0.0.5   |



### 依赖库：

```
Package            Version
------------------ -------
click              8.3.0
colorama           0.4.6
deepmerge          2.0
Markdown           3.10
pip                25.3
Pygments           2.19.2
pymdown-extensions 10.16.1
PyYAML             6.0.3
```



## 部署教程

### 使用`zensical`进行部署

1. 确保有python环境(>=3.12)

2. 克隆本项目到本地
    ```shell
    git clone https://github.com/apocfly/Operating-document.git
    ```

3. 创建虚拟环境  

   你也可以使用conda或者pdm之类的包管理软件, 这里我们使用python原生的venv做示范

    ```shell
    python -m venv ./.venv
    ```

4. 激活虚拟环境
    ```cmd
    ; cmd
    .\.venv\Scripts\activate.bat
    ```

    ```powershell
    ; powershell
    .\.venv\Scripts\activate
    ```

5. 安装所需的库

    ```shell
    pip install -r requirements.txt
    ```

6. 运行开发服务器
    ```shell
    zensical serve
    ```

7. 进行编写



### 使用bat脚本部署

1. 运行项目根目录下的`DevEnv-Launcher.bat`一键配置环境及打开Vscode

2. 运行开发服务器

   ```shell
   zensical serve
   ```

3. 进行编写



### 添加requirements.txt

1. 安装freeze

   ```shell
   pip freeze
   ```

2. 生成requirements.txt

   ```shell
   pip freeze > requirements.txt
   ```



### 更新Zensical

1. 前往[Github releases](https://github.com/zensical/zensical/releases)查看版本

2. 更新Zensical

    ```shell
    pip install --upgrade --force-reinstall zensical
    ```

3. 参考[添加requirements.txt](#添加requirementstxt) 更新requirements.txt



## 贡献方式

您可以将本项目进行 [fork](https://github.com/apocfly/Operating-document/fork)，并查看 [#3](https://github.com/apocfly/Operating-document/issues/3) 内的Todo list以查看需要完成的任务



## 文件分类的说明

本文档站有许多分文件夹，以下将讲述他们的用途：

```markdown
General - 总则，通适用于任何用户的文件
CTD - 管制员训练部，培训管制员所用到的材料等
	Learning_Center - 学习中心，培训管制员所用到的一些理论资料
PTD - 飞行员训练部，培训飞行员所用到的材料等
Document - 文档，存放上述Markdown文件的docs、pdf格式文件
```



## 适用的平台

目前我们已经将这套方案启用于“APOCFLY 天启模拟飞行平台”上，您可以[点此](https://qm.qq.com/q/5qyq2c4n9m)加群。



## 许可证

本项目的全部文字在 <a href="https://creativecommons.org/licenses/by-sa/4.0/deed.zh-hans" target="_blank" rel="noopener noreferrer">CC BY-SA 4.0(知识共享 署名-相同方式共享 4.0协议)</a> 之条款下提供，附加条款亦可能应用。

```markdown
本项目采用 [知识共享署名-相同方式共享 4.0 国际许可协议 (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/deed.zh-hans) 授权。

您可以自由地：

- 分享 — 在任何媒介以任何形式复制、发行本作品
- 演绎 — 修改、转换或以本作品为基础进行创作

惟须遵守以下条件：

- **署名** — 您必须给予适当的署名，提供许可协议链接，并指明是否作了修改。
- **相同方式共享** — 若您再混合、转换或者基于本作品进行创作，必须基于与原先许可协议相同的许可分发。

完整协议请参见 [https://creativecommons.org/licenses/by-sa/4.0/deed.zh-hans](https://creativecommons.org/licenses/by-sa/4.0/deed.zh-hans)。
```



---



## 社区行为准则

在[CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)中查阅，请注意这里是COC是指Github社区的行为准则，而不同于模拟飞行的COC。
