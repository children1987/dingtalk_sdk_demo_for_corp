# dingtalk-django-example

本项目是使用django、celery、[dingtalk-sdk](http://github.com/007gzs/dingtalk-sdk "dingtalk-sdk")开发 钉钉企业接入的demo。

项目初始化
----------
- 本项目依赖 mysql 和 redis 请先准备好相应环境
- 下载项目 `git clone https://github.com/children1987/dingtalk_sdk_demo_for_corp.git`
- 创建配置文件 `example/local_settings.py` 参考 `example/local_settings.py.default` 进行配置
- 初始化项目 
```
# 安装依赖
pipenv install -r requirements.txt

# 初始化数据库
pipenv run python manage.py makemigrations
pipenv run python manage.py migrate

# 创建超管用户
pipenv run python manage.py createsuperuser

# 在服务器上运行程序
pipenv run python manage.py runserver 0.0.0.0:8000
```

企业接入
--------
- 在钉钉后台配置ip或域名白名单。
- 登录 `http://ip:8000/admin/`。
- 访问 `http://ip:8000/api/dingtalk/corp/test/sync/corp` 可将企业员工同步到对应User表中。
- 可以通过`http://ip:8000/admin/corp/user/`查看。
