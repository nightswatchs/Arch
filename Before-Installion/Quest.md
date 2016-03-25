* 一边分区一边挂载，还是先分区再挂载？
  * 先分区后挂载
* 如果安装单系统的话那些命令是和这个相关的？
  * 一样的吧
  * 应该是mbr哪个不一样
* parted命令到底是个什么鬼？
  * Must be started with parted device(/dev/sda)(进入交互模式)
  * mklabel 创建分区表(使用MBR还是GPT)
  * mkpart PART-TYPE(primary/extended～) [FS-TYPE]ext4.. START extended
  * linux-swap
  * print ：输出分区信息
  * 例如：
    * parted /dev/sda
    * mklabel gpt
    * set 1 boot on
    * mkpart primary ext4 start end
  * 注意GiB和MiB
* (parted)...什么鬼意思？
  * 进入交互模式
* 采用哪种文件系统？
  * ext4
* ～不能选吗，选择分区？
* ～怎么格式化分区？
  * mkfs.ext4 /dev/sdxy
* ～不需要挂载/ /home 吗？
  * 好像没说哈，难道自动挂载了？或者不用挂载，你傻了啊。
  * 相同的原理一起做吧。
* ～上述步骤完成之后干什么呢？
  * 不用你费心
* ～安装需要注意那些方面？
* ～先安装什么，然后安装什么？
  * 格式化后把分区挂载到/mnt，然后用pacstrap来安装基本的系统到/mnt，再chroot进入到mnt中，配置好引导启动什么的，然后退出，卸载mnt，重启取出安装介质。
* ～语言在哪里设置？
  * Locale(language,currency denomination, numerology, character sets)
  * possible values are listed in */etc/locale.gen*
  * generate the new locales: **locale-gen**
* ～使用什么编辑器 修改文件？
* ～写哪个时区？
* ～nano怎么用，能用vi吗
  * ctrl+o(保存)
  * ctrl+x(退出)
  * 不能用vi就用nano
* ～怎么用pacman安装package？
  * pacman -S package_name #安装软件包
* ~i386-pc
  * 32,64都是用这个
