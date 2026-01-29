# Openlist的QQ闪传文件导入版本

> 为`openlist`适配了QQ闪传文件的导入功能

#### 背景

当`openlist`部署的公网服务器**带宽过小**的时候，上传文件到**本地存储**（尤其是大文件）就会非常难受，本项目产生的意义就是为了**解决上传本地存储过慢**的问题（H3CoF6遇到的问题其实是**校园网过于拉跨**，scp的速度没有上传QQ，`napcat`下载的速度快）

![image-20260129233026166](C:\Users\17078\AppData\Roaming\Typora\typora-user-images\image-20260129233026166.png)

#### 项目feature

1. 引入QQ原生**深链接**，直接唤醒闪传发送页面，非常方便

2. 自能解析**多种分享链接格式**，包括：

   - 分享链接
   - 分享口令
   - 文件集ID

3. 引用`Openlist`**其它网盘的代码**，完成文件夹结构预览，流畅无感

   > 因为QQ闪传本来就具有一定的网盘特性

4. 自定义选择文件，利用**离线下载任务，快速并发完成下载导入**

#### 快速使用

没有提供预编译的二进制文件，需要使用本项目**请自行部署**

1. **编译前端**

   - `cd frontend`
   - `pnpm i`
   - `npm run build`

   ==最好不要用build脚本，大概率跑不通（git目录修改了），需要中文翻译请自行下载==

2. **编译后端**

   - `go install`
   - `go build`

   ==同样不推荐使用build.sh脚本==

3. **编译完成后**，二进制文件应该在backend目录：

   - start启动服务器（默认端口5244）
   - admin random 重置超管密码

#### 项目截图

1. 深链接：
   ![image-20260129234023148](C:\Users\17078\AppData\Roaming\Typora\typora-user-images\image-20260129234023148.png)
2. 文件夹结构预览和选择
   ![image-20260129234147106](C:\Users\17078\AppData\Roaming\Typora\typora-user-images\image-20260129234147106.png)
3. 离线下载导入
   ![image-20260129234243746](C:\Users\17078\AppData\Roaming\Typora\typora-user-images\image-20260129234243746.png)

#### 说明

本项目**不再随`openlist`主仓库更新**，<del>并且因为不可言说的原因无法合并</del>，所以本仓库的定位只是一个  **个人，小众需求实现的项目**  ，请不要大范围推广啊啊啊！！！