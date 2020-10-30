# Web 版测试报告配置说明

## 一、安装 docsify

1. 安装 nodejs

2. 安装 docsify：请在 cmd 里执行如下命令行

    ```bash
    npm i docsify-cli -g
    ```
## 二、生成测试报告目录

1. 生成 report 目录：请在合适的目录（如 `D:\` 盘）打开 cmd，执行如下命令行

    ```bash
    report
    ```

2. 启动网站，在该目录（如 `D:\report` 盘）打开 cmd，执行如下命令行

    ```bash
    docsify serve
    ```
    在浏览器中打开：http://localhost:3000


## 三、自动化测试接入 Web 测试报告

1. snapshot 映射到 Web 目录

打开 cmd，执行如下命令行

```bash
mklink /j D:\report\report\snapshot D:\sweetest_example\snapshot
```

注意，命令行中 D:\report 为 report 目录，D:\sweetest_example 为自动化测试目录，请根据实际目录更换

2. 请在启动脚本（如：start.py）里 `sweet.plan()` 后面添加生成测试报告的代码

```Python
# 执行自动化测试
sweet.plan()

# 生成 Web 测试报告，'D:\report' 为 report 生成的目录
sweet.report(r'D:\report')
    ```

3. 执行自动化测试

4. 查看 Web 测试报告

请确保已经按之前步骤启动了网站

在浏览器中打开：http://localhost:3000