myMallBackend
=================

本地开发环境部署
--------
1. 安装mysql数据库服务端(推荐5.7+),并设置为utf-8编码，创建相应DataFactoryBackend数据库，设置好相应用户名、密码，启动mysql

2. 修改:MyMallBackend/settings.py里DATABASES字典和邮件发送账号相关配置
   ```
        DATABASES = {
            'default': {
                'ENGINE': 'django.db.backends.mysql',
                'NAME': 'datafactory',  # 新建数据库名
                'USER': 'root',  # 数据库登录名
                'PASSWORD': '123456',  # 数据库登录密码
                'HOST': '127.0.0.1',  # 数据库所在服务器ip地址
                'PORT': '3306',  # 监听端口 默认3306即可
            }
        }
    ```

3. 命令行窗口执行pip install -r requirements.txt 安装工程所依赖的库文件

4. 生成数据库迁移脚本,并生成表结构
    ```bash
        python manage.py makemigrations #生成数据迁移脚本
        python manage.py migrate  #应用到db生成数据表
    ```

5. 启动服务
    ```bash
        python manage.py runserver 0.0.0.0:9000
    ```







