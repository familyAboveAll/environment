## 项目目录

```
├── src
    ├── components 组件
        ├── PageHeaderWrapper 面包屑
    ├── layouts 通用布局
        ├── BasicLayout.js 基础页面布局，包含了头部导航，侧边栏和通知栏
        ├── Footer.js footer内容
        ├── UserLayout.js 抽离出用于登陆注册页面的通用布局
    ├── locales 配置集合
        ├── zh-CN 配置文件夹
            ├── form.js 表单文字集合
            ├── login.js 注册页面文字集合
            ├── menu.js menu的菜单名
            ├── settingDrawer.js 设置主题文字集合
            ├── setting.js 用户设置文字集合
        ├── zh-CN.js 配置入口
    ├── models
└── config
    ├── router.config.js 路由管理
```

## Pro 扩展配置

### router.config.js 扩展了一些关于 pro 全局菜单的配置。

```
{
  name: 'dashboard',
  icon: 'dashboard',
  hideInMenu: true,
  hideChildrenInMenu: true,
  hideInBreadcrumb: true,
  authority: ['admin'],
}
菜单根据 router.config.js 生成，具体逻辑在 src/models/menu.js 中的 formatter 方法实现。
```
> * name: 当前路由在菜单和面包屑中的名称，注意这里是国际化配置的 key，具体展示菜单名可以在 /src/locales/zh-CN.js 进行配置。
> * icon: 当前路由在菜单下的图标名。
> * hideInMenu: 当前路由在菜单中不展现，默认 false。
> * hideChildrenInMenu: 当前路由的子级在菜单中不展现，默认 false。
> * hideInBreadcrumb: 当前路由在面包屑中不展现，默认 false。
> * authority: 允许展示的权限，不设则都可见，详见：权限管理。
