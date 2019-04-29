# Fuck-Login !

> 2019-03-21 给自己定个小计划，每周更新一个站点的登陆脚本

### 1.介绍

#### 提供常见站点的模拟登陆

#### 前言

由于`xchaoinfo/fuck-login`的项目不再维护了

所以利用业余时间参考`xchaoinfo`大神的代码重新做起一些常见站点的登录，希望一起交流学习。

#### 登陆方式

- 多数采用`requests`库创建会话`session`进行登陆
- 必要的`js`生成参数多采用`PyExecJS`，部分`js`代码过长会采用`Selenium`控制浏览器进行运行
- 尽量不采用`Selenium`进行自动化操作登陆
- 能力有限，水平一般。机器学习刚开始踩坑中，若登陆验证码的识别需要模型识别才能解决的话，暂时采用手动输入方案；若可通过`OCR`进行识别，会提提简单的处理思路。

### 2.程序结构

```python
import requests


class LoginWebsiteName:
    """
    登录程序结构
    """
    # 登录操作会话对象
    session = requests.session()

    def __init__(self, username: str, password: str, **kwargs):
        self.username = username
        self.password = password
        pass

    def login(self) -> dict:
        """
        执行登录操作
        :return: `rtype:dict` 登录结果
        """
        pass

    def get_user_info(self) -> dict or None:
        """
        获取用户信息
        :return: 登录成功`rtype:dict`, 登录失败`rtype:None`
        """
        pass

    def get_login_cookies(self) -> dict:
        """
        获取用户登录后的cookies
        :return:
        """
        pass


if __name__ == '__main__':
    test_name = 'your username'
    test_password = 'your password'
    login_obj = LoginWebsiteName(username=test_name, password=test_password)
    # 开始执行登录操作
    login_result = login_obj.login()
    # 获取用户信息
    user_info = login_obj.get_user_info()
    # 获取登录状态cookies
    cookies = login_obj.get_login_cookies()
```






