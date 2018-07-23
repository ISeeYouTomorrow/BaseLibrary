## BaseLibrary ##

  本库旨在开发项目时能快速搭建框架，提供较为常用的开发工具。建议下载作为依赖库，
  不要远程依赖，便于修改。部分功能会仅在demo中有体现，请详细看完demo。
-----------------------------------------------------
  下面介绍本库的主要内容
### 1. MVP模式(变种) ###
  View ：Activity/Fragment

  Contract ：用来连接 View 和 Presenter

  Presenter ：执行代理

 使用方法:

    1.继承BaseActivity/BaseFragment/BaseDialogFragment
    2.写好Presenter泛型，实现View接口
    3.重写createPresenter() 方法创建，getPresenter()获取对象

Base 大致功能如下：

    1.切换语言
    2.切换日夜模式
    3.检测横竖屏
    4.显示/隐藏Loading弹框
    5.ButterKnife 绑定数据
    6.控制RxJava生命周期，防止内存泄漏
    7.MVP模式 参考 https://github.com/north2016/T-MVP
    需要时 可重写createPresenter() {@link BaseActivity#createPresenter()}  并且使用泛型 <P extends BasePresenter> 为当前Presenter实例
    详情请查看源码。

### 2. Refresh + RecyclerView + Adapter ###
 刷新推荐使用的是: [SmartRefreshLayout](https://github.com/scwang90/SmartRefreshLayout)
 Adapter推荐使用: [BaseRecyclerViewAdapterHelper](https://github.com/CymChad/BaseRecyclerViewAdapterHelper),
 可直接继承本项目的BaseRVAdapter,更方便 。用到选择逻辑时可继承 SelectedAdapter 。
### 3. 各基础常用的Dialog ###
    BottomListDialog 类似BottomSheetDialog,从底部弹窗的选择框
    LoadingDialog 加载框
    PromptDialog/PromptDialogFragment 提示框

### 4. 各基础常用的自定义View ###
    NoScrollViewPager 可不能滑动的ViewPager
    SwipeItemLayout 侧滑多选项,类似QQ
    ClickImageView 点击可变色阴影的ImageView
    TimerTextView 获取验证码 倒计时View 语言需自己处理
    SquareFrameLayout/SquareLinearLayout 可用ConstraintLayout代替

### 5. 网络加载 Retrofit + OkHttp + RxJava ###
    网络加载使用 Retrofit + OkHttp + RxJava 配套方案，可以控制加载框，
    RxJava生命周期绑定,拦截器加密,数据泛型解析。

### 6. Socket通信工具 ###
    可创建TCP/UDP连接


### 7. 其他工具（详情见utils包下文件） ###
     1.AppUtil  App信息、软键盘等。
     2.SPUtil BaseSPManager SharedPreferences工具类和管理类
     3.BitmapUtil
     4.ContextUtil 获取文字，颜色
     5.DisplayUtil ScreenUtil 屏幕像素相关
     6.EmptyUtil 空字符串 /数组判断工具
     7.ToastUtil 吐司工具
     8.RxPermissionsUtil 权限申请
     9.RegularUtil 正则工具
     等...


### 8. 蓝牙开发（待更新） ###

##  关于模板 ##
    项目 localTemplates 目录下的二个模板请Copy到 AndroidStudio安装目录下的模板路径:
    某盘:\AndroidStudio安装路径\plugins\android\lib\templates\activities 。
    例：我的studio安装路径在C:\AndroidStudio, 找到该目录下的
    \plugins\android\lib\templates\activities ,copy进去 重启sudio 即可生效


### Log更新日志 ###
    *2018-7-23 添加说明文档