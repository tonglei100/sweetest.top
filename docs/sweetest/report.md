# Web 版测试报告使用帮助

## 安装 Web 版测试报告

1. 安装 nodejs

2. 安装 docsify：请在 cmd 里执行如下命令行

    ```bash
    npm i docsify-cli -g
    ```

3. 生成 report 目录：请合适的目录（如 `D:\` 盘）打开 cmd，执行如下命令行

    ```bash
    report
    ```

4. 在该目录（如 `D:\report` 盘）打开 cmd，执行如下命令行

    ```bash
    docsify serve
    ```

## 自动化测试接入 Web 测试报告 

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
