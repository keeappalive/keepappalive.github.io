## *MIUI*<span id="miui"></span>

### 关闭省电模式

1. 打开设置，点击**电池与性能**；
2. 关闭**省电模式**和**超级省电;**
3. 点击自动任务，进入后选择将自动任务情景都设置为关闭。

![](/1.jpg)![](/2.jpg)![](/3.jpg)![](/4.jpg)

### 选择后台无限制

1. 打开设置，点击 **应用设置**>**应用管理**；
2. 找到小米穿戴APP，点击进入；
3. 点击**省电策略**，进入后选择 **无限制**。

![](/5.jpg)![](/6.jpg)![](/7.jpg)![](/8.jpg)![](/9.jpg)

### 允许应用自启动

1. 打开设置，点击**应用设置**>**应用管理**；
2. 找到小米穿戴APP，点击进入；
3. 选择 **自启动**，将其打开。

![](/10.jpg)![](/11.jpg)![](/12.jpg)![](/13.jpg)

### 后台进程锁定

![](/14.jpg)![](/15.jpg)

----------------------------------

## *EMUI*<span id="emui"></span>

### 允许程序自启动

1. 打开手机管家，选择 应用启动管理，点击进入；
2. 找到小米穿戴，并将开关设置为关闭状态；同时在弹出的手动管理弹窗中，将自启动、关联启动、后台活动全部勾选。

![](/16.jpg)![](/17.jpg)

若按照以上方法无法设置，请尝试按照如下步骤进行设置：


1. 打开手机的系统设置；
2. 选择 应用 > 应用启动管理；
3. 找到小米穿戴，并打开开关。

### 后台进程锁定

1. 打开手机 最近打开的程序 页面；
2. 将小米穿戴APP下拉，在APP上方出现锁定的标志即可。

![](/18.jpg)

### 电源管理

1. 打开手机的系统设置；
2. 在搜索框中搜索 电池优化；
3. 点击进入电池优化，将左上角的过滤选择为 所有应用；
4. 找到小米穿戴，选择 不允许，点击 确定。

![](/19.jpg)![](/20.jpg)![](/21.jpg)![](/22.jpg)

----------------------------------

## *Color OS*[](#coloros)<span id="miui"></span>

### 允许应用自启动

1. 打开手机管家，在手机管家中找到 权限隐私；
2. 在权限隐私中找到 自启动管理，点击进入；
3. 在程序列表中找到小米穿戴，并打开开关。

![](/23.png)![](/24.png)![](/25.png)

### 锁定应用

1. 打开手机 最近打开的程序 页面；
2. 将小米穿戴APP下拉，在APP卡片上方出现锁定的标志即可。

![](/26.png)

### 关闭耗电保护

1. 打开系统设置，点击 电池；
2. 点击 耗电保护；
3. 找到小米穿戴，点击进入;
4. 关闭后台冻结以及自动优化开关，如有深度睡眠开关也请关闭。

![](/27.png)![](/28.png)![](/29.png)![](/30.png)

----------------------------------

## *Funtouch OS*[]<span id="funtouchos"></span>

### 允许应用自启动

1. 打开i管家，点击 应用管理；
2. 在应用管理界面点击 权限管理 ；
3. 在权限管理中找到 自启动；
4. 在自启动管理中找到小米穿戴，并打开开关。

![](/31.jpg)![](/32.jpg)![](/33.jpg)![](/34.jpg)

### 后台进程锁定

1. 打开手机 最近打开的程序 页面；
2. 将小米穿戴APP下拉，在APP卡片上方出现锁定的标志即可。

![](/35.jpg)

### 关闭耗电保护

1. 打开手机设置，点击 电池；
2. 选择后台高耗电；
3. 找到小米穿戴，并开启权限。

![](/36.jpg)![](/37.jpg)![](/38.jpg)

----------------------------------

## *其他手机*<span id="other"></span>

1. 在最近打开的程序页面中锁定小米穿戴APP；
2. 在安全中心或手机设置中找到自启动管理，然后找到小米穿戴，并打开开关；
3. 在安全中心或手机设置中将小米穿戴加入其白名单；
4. 若手机中安装了相关的应用休眠工具，如绿色守护、自启管家等应用，则需要将小米穿戴从这些休眠应用列表中删除。

----------------------------------

## *Android开发者看这里*

1. 在使用之前，你需要知道，这只是一个静态网页，并没有任何逻辑存在，不过你可以使用 https://keepappalive.com/#xxx 来跳转相应的系统UI，例如 https://keepappalive.com/#miui 。
2. 下面提供引导用户跳转相关UI的路径代码，因为网页能力限制，所以没有添加任何直接跳转到系统页面的按钮。
3. 本站不会保存任何使用者的任何信息，但是本网页存放在 https://coding.net 上，您和您的用户的IP可能会被记录，请知晓。

<details>
```java
        String brand = android.os.Build.BRAND;
        Log.e("SettingUtils","brand="+brand);
        switch (brand.toLowerCase()){
            case "samsung":
                componentName = new ComponentName("com.samsung.android.sm",
                        "com.samsung.android.sm.app.dashboard.SmartManagerDashBoardActivity");
                break;
            case "honor":
            case "huawei":
                componentName = new ComponentName("com.huawei.systemmanager",
                        "com.huawei.systemmanager.startupmgr.ui.StartupNormalAppListActivity");
                break;
            case "xiaomi":
                componentName = new ComponentName("com.miui.securitycenter",
                        "com.miui.permcenter.autostart.AutoStartManagementActivity");
                break;
            case "vivo":
                componentName = new ComponentName("com.iqoo.secure",
                        "com.iqoo.secure.ui.phoneoptimize.AddWhiteListActivity");
                break;
            case "oppo":
                componentName = new ComponentName("com.coloros.oppoguardelf",
                        "com.coloros.powermanager.fuelgaue.PowerUsageModelActivity");
                break;
            case "360":
                componentName = new ComponentName("com.yulong.android.coolsafe",
                        "com.yulong.android.coolsafe.ui.activity.autorun.AutoRunListActivity");
                break;
            case "meizu":
                componentName = new ComponentName("com.meizu.safe",
                        "com.meizu.safe.permission.SmartBGActivity");
                break;
            case "oneplus":
                componentName = new ComponentName("com.oneplus.security",
                        "com.oneplus.security.chainlaunch.view.ChainLaunchAppListActivity");
                break;
            default:
                break;
        }
```
</details>
