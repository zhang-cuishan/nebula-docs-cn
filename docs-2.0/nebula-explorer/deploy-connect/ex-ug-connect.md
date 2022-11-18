# 连接数据库

在成功启动 Explorer 后，用户需要配置连接 Nebula Graph。本文主要描述 Explorer 如何连接 Nebula Graph 数据库。

## 前提条件

在连接 Nebula Graph 数据库前，用户需要确认以下信息：

- 已经安装部署了 Explorer。详细信息，参见[部署 Explorer](../deploy-connect/ex-ug-deploy.md)。

- Nebula Graph 的 Graph 服务本机 IP 地址以及服务所用端口。默认端口为 `9669`。

- Nebula Graph 数据库登录账号信息，包括用户名和密码。

## 连接数据库

按以下步骤连接 Nebula Graph 数据库：

1. 在 Explorer 的**配置数据库**页面上，输入以下信息：

   - **Host**：填写 NebulaGraph 的 Graph 服务本机 IP 地址及端口。格式为 `ip:port`。如果端口未修改，则使用默认端口 `9669`。

    !!! Note

        - 即使 NebulaGraph 数据库与 Explorer 部署在同一台机器上，用户也必须在 **Host** 字段填写这台机器的本机 IP 地址，而不是 `127.0.0.1` 或者 `localhost`。
        - 在新的标签页连接另一个 NebulaGraph 数据库时，会覆盖旧标签页的会话。如果需要同时登录多个 NebulaGraph 数据库，可以用不同的浏览器或者无痕模式。

   - **用户名**和**密码**：根据 NebulaGraph 的[身份验证](../../7.data-security/1.authentication/1.authentication.md)设置填写登录账号和密码。
     - 如果未启用身份验证，可以填写默认用户名 `root` 和任意密码。
     - 如果已启用身份验证，但是未创建账号信息，用户只能以 GOD 角色登录，必须填写 `root` 及对应的密码 `nebula`。
     - 如果已启用身份验证，同时又创建了不同的用户并分配了角色，不同角色的用户使用自己的账号和密码登录。

2. 完成设置后，点击**登录**按钮。

  !!! note

        一次连接会话持续 30 分钟。如果超过 30 分钟没有操作，会话即断开，用户需要重新登录数据库。

## 断开连接

在页面右上角，选择![icon](https://docs-cdn.nebula-graph.com.cn/figures/image-icon10.png)图标 > 清空连接。

如果浏览器上显示**配置数据库**页面，表示 Explorer 已经成功断开了与 Nebula Graph 数据库的连接。
