# CUHK(SZ) VPN script 

主要功能：一键连接vpn (Cisco anyconnect),免输密码

Ref: [Github.Cisco_anyconnect.ps1@jhorsman](https://gist.github.com/jhorsman/88321511ce4f416c0605)



## Component:

`connect.cuhksz.ps1`

`disconnect.cuhksz.bat`



## Prerequisites:

1. Already installed Powershell | 已经有Powershell

   

2. Already setup Powershell script execution permission(Optional)  |  已经配置好Powershell脚本运行权限(可选)

   ```
   Maybe you'll encounter problem like:	
   "cannot run activate.ps1 because running scripts is disabled on the system" 
   Solution:
   Use admin to run Powershell, type "set-ExecutionPolicy", press Enter;
   Then type "Y", press Enter.
   Done.
   ```

   ```
   也许你会遇到这样的报错：
   "无法运行***.ps1,因为在此系统中禁止执行脚本。"
   解决方案：
   以管理员身份运行Powershell, 执行命令set-ExecutionPolicy RemoteSigned,再按Y即可。
   
   本步骤只需要在第一次配置时运行。
   ```

   [Reference](https://www.jb51.net/article/95022.htm)

   

3. Edit `connect.cuhksz.ps1`, replace model as your personal info. | 修改`connect.cuhksz.ps1` 中的line12, line13 ，将其改为你的学号和密码。

   ```
   param (
     [string]$Server = $( "vpn.cuhk.edu.cn" ),
     [string]$Group = $( "0" ),
     [string]$User = $( "120000000" ),
     [string]$Password = $( "MyPassWord" )
   )
   ```

   Change the template "120000000" to your student number and the template "mypassword" to your password. Save it. | 将模板“120000000”改为你的学号，将模板“Mypassword”改为你的密码，保存。

   

4. Confirm that your Cisco anyconnect is installed at the following address: | 确认你的Cisco AnyConnect是否安装在以下地址：

   ```
   [string]$vpncliAbsolutePath = 'C:\Program Files (x86)\Cisco\Cisco AnyConnect Secure Mobility Client\vpncli.exe'
   [string]$vpnuiAbsolutePath  = 'C:\Program Files (x86)\Cisco\Cisco AnyConnect Secure Mobility Client\vpnui.exe'
   ```

   The above is the general default installation address. If not, please modify it in time. | 上为一般默认安装地址。若不是，请及时修改。



## How to run？

You can put ` connect.cuhksz.ps1` `disconnect.cuhksz.bat ` anywhere like on the desktop.

你可以把`connect.cuhksz.ps1` `disconnect.cuhksz.bat`放在桌面等任意位置。

#### Connect | 连接：

Right click ` connect.cuhksz.ps1 `, click "run with PowerShell" to complete the connection.

右键`connect.cuhksz.ps1` ，点击”使用Powershell运行“即可完成连接。

#### Disconnect | 断开：

Double click `disconnect.cuhk.bat`.

直接双击`disconnect.cuhksz.bat`。

