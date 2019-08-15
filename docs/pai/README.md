Pai 是一款极简 RPA 框架


# 快速启动

- 在本机安装 MongoDB

- 启动 server

```shell
cd server
python app.py
```

- 启动 agent

```shell
cd agent
python app.py
```


# 测试

## 创建计划 

- 编辑 api.py 文件，取消 --- NEW PLAN --- 段的代码注释，注释其他部分
- 执行 api.py

```shell
python api.py
```

## 查询计划列表 

- 编辑 api.py 文件，取消 --- QUERY PLAN LIST --- 段的代码注释，注释其他部分
- 执行 api.py

```shell
python api.py
```

## 查询计划详情 

- 编辑 api.py 文件，取消 --- QUERY PLAN --- 段的代码注释，注释其他部分
- 从上一步中，取一个 `_id` 的值，替换本段的 `_id` 值
- 执行 api.py

```shell
python api.py
```

## 执行计划

- 编辑 api.py 文件，取消 --- CALL PLAN --- 段的代码注释，注释其他部分
- 从上一步中，取一个 `_id` 的值，替换本段的 `_id` 值
- 执行 api.py

```shell
python api.py
```

## 查询任务列表 

- 编辑 api.py 文件，取消 --- QUERY TASK LIST --- 段的代码注释，注释其他部分
- 执行 api.py

```shell
python api.py
```

备注：当 query 中有 {'newest': 'Y'} 时，为查询最新任务，没有是查询所有历史任务。


## 查询计划详情 

- 编辑 api.py 文件，取消 --- QUERY TASK --- 段的代码注释，注释其他部分
- 从 *执行计划* 或 *查询任务列表* 的返回值中，取 `_id` 的值，替换本段的 `_id` 值
- 执行 api.py

```shell
python api.py
```


# 函数调用

Pai 是通过调用 agent 上的函数来执行任务的。函数应该放在 agent/lib 目录。
编写计划步骤时，主要的调用参数如下：

```python
{'agent': 'FUND', 'moudle': 'files', 'function': 'exists', 'data':{'dir': '', 'path': 'app.py'}}
```

其中 files 就是 lib 的文件名，exists 就是 files.py 文件中的函数名，data 是 exists 函数的实参。

备注：files.py 是一个测试文件，其中加入随机等待时间，方便测试时观察。