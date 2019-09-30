1.`pod install/setup失败`
1.1`pod setup`：
```
Setting up CocoaPods master repo
  $ /usr/bin/git clone https://github.com/CocoaPods/Specs.git --progress --
  master
  Cloning into 'master'...
  remote: Enumerating objects: 2233, done.
  remote: Counting objects: 100% (2233/2233), done.
  remote: Compressing objects: 100% (2156/2156), done.
  error: RPC failed; curl 56 LibreSSL SSL_read: SSL_ERROR_SYSCALL, errno 54
  fatal: the remote end hung up unexpectedly
  fatal: early EOF
  fatal: index-pack failed
[!] /usr/bin/git clone https://github.com/CocoaPods/Specs.git --progress -- master

Cloning into 'master'...
remote: Enumerating objects: 2233, done.
remote: Counting objects: 100% (2233/2233), done.
remote: Compressing objects: 100% (2156/2156), done.
error: RPC failed; curl 56 LibreSSL SSL_read: SSL_ERROR_SYSCALL, errno 54
fatal: the remote end hung up unexpectedly
fatal: early EOF
fatal: index-pack failed
```
1.2`Pod install报错`
报错记录：
```
[!] CocoaPods could not find compatible versions for pod "WeexSDK":
  In Podfile:
    WeexSDK (= 0.16.3)

None of your spec sources contain a spec satisfying the dependency: `WeexSDK (= 0.16.3)`.

```
处理：更改podfile中weexsdk的版本

1.3`pod install速度太慢`

2.cocoapods安装
报错记录：
```
sudo gem install cocoapods
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /usr/bin directory.

```
处理：`sudo gem install cocoapods -n /usr/local/bin`
[参考连接](https://stackoverflow.com/questions/50422786/you-dont-have-write-permissions-for-the-usr-bin-directory-while-installing-co)

3.Weex不完全记录

3.1 web端可以正常显示weex扫描为空白

3.2 alert显示参数缺失无法显示

4.修复ios端报错
product->clean build  folder



