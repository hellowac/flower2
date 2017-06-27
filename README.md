
## dcs_flower

从 [celery flower]() 二次开发而来. 具体文档参考: [flower.readthedocs.io](http://flower.readthedocs.io/en/latest/index.html)

二次开发的新功能:

- 任务详细页面 `retry` 功能.

*命令行参数均未改变.*

但默认参数的值有改变.

参数 | 原默认值 | 现默认值 | 备注
-----|---------|----------|------
`DEFAULT_CONFIG_FILE` | `flowerconfig.py` | `dcs_flowerconfig.py` | 默认配置文件
`persistent` | `False` | `True` | 数据是否持久化
`db` | `flower` | `dcs_flower.db` | 数据持久化时的数据文件名

在项目中使用的四种方法:

- **指定`celery`项目的`broker`地址:**
  - `dcs_flower -b broker_addr`  -> `dcs_flower -b redis://localhost:6379/0`
  - `dcs_flower --broker=broker_addr` -> `dcs_flower --broker=redis://localhost:6379/0`
- **在`celery`中启动:**
  - `celery dcs_flower -A proj` -> `celery dcs_flower -A flower_task`
  - `celery dcs_flower -app=proj` -> `celery dcs_flower -app=flower_task`


*默认持久化.*

*其余参数参考:[flower.readthedocs.io](http://flower.readthedocs.io/en/latest/index.html)*
