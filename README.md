# OpenHarmony-NOTE
## 环境配置

### RK3568

- 在烧录大禹时，在接线没有问题的情况下遇到了通信问题，是 `MASKRAM` 模式，通过按住 `RESET` 和 `VOL+` 两个键再加电，然后依次松开 `RESET` 和 `VOL+` 进入 `LOADER` 模式即可解决问题。

  https://www.nutpi.net/thread?topicId=660

### K1

- 执行 `repo sync -j4 -c --fail-fast` 时出现以下错误：

  ```shell
  shellerror.GitError: Cannot checkout applications_app_samples: Cannot initialize work tree for applications_app_samples
  ```

  需要下载 `git-lfs` 工具：

  ```shell
  sudo apt-get install git-lfs
  ```

  https://bbs.huaweicloud.com/blogs/346014

- 完整编译运行如下指令时：

  ```shell
  ./build.sh --product-name musepi --ccache --prebuilt-sdk
  ```

  出现错误：

  ```shell
  [OHOS ERROR] Code:        0000
  [OHOS ERROR] 
  [OHOS ERROR] Reason:      find component prebuilt_hap failed, please check it in /home/dongfanqing/WorkSpace/oh5/out/preloader/ohos-sdk/parts.json.
  [OHOS ERROR] 
  [OHOS ERROR] Error Type:  UNKNOWN ERROR TYPE
  [OHOS ERROR] 
  [OHOS ERROR] Description: NO DESCRIPTION
  [OHOS ERROR] 
  [OHOS ERROR] Solution:    NO SOLUTION
  [OHOS ERROR] 
  [OHOS ERROR] ohos-sdk build failed! You can try to use '--no-prebuilt-sdk' to skip the build of ohos-sdk.
  ```

  原因在于使用系统 Ubuntu 24.04 ，系统中 `apt-get install` 不再支持 `Python2` 等，导致开始环境有残缺，使用 Ubuntu 22.02 可以顺利解决问题。

- 完整编译遇到问题：

  ```shell
  [OHOS ERROR] Code:		  4000
  [OHOS ERROR]
  [OHOS ERROR] Reason:	  COMPILE Failed! Please check error in /home/yangshiyu10/ohos/oh5/out/musepi/error.log, and forbuild information in /home/yangshiyu10/ohos/oh5/out/musepi/butld.logmore
  [OHOS ERROR]
  [OHOS ERROR] Error Type:  Ninja build errorГOHOSERROR][OHOSERROR]Description: An unknown error occurred while executing 'ninja -c'.
  [OHOS ERROR]
  [OHOS ERROR] Solution:	  no solution
  [OHOS ERROR]
  ```

  

