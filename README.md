# magisk-mipay-RedMiNote8pro-begonia

## 自行制作Magisk Module

其他**MIUI(>=11)**机型也可以这么做：

```bash
git clone https://github.com/ahxxm/magisk-mipay-redmi-note8pro.git
cd magisk-mipay-redmi-note8pro

# 从"国内版"固件提取: https://miuiver.com/begonia_recovery/
git clone https://github.com/wych42/mipay-extract
cd mipay-extract
wget https://bigota.d.miui.com/V11.0.3.0.QGGCNXM/miui_BEGONIA_V11.0.3.0.QGGCNXM_b656ebe642_10.0.zip
./extract.sh
unzip mipay-BEGONIA-V11.0.3.0.QGGCNXM.zip
cd ../

# 更新apk和打包
cp -r mipay-extract/system/app/* system/app/
zip -r mipay-redmi-note8-pro.zip META-INF system config.sh module.prop system.prop
```

然后到Magisk Manager里安装`mipay-redmi-note8-pro.zip`。

## 参考

[MIUI 国际版/EU 版本地化教程 - 小米钱包篇
](https://sspai.com/post/60065)： 可惜最重要的“制作 Magisk 模块”已经过时

[小米9 Pro 5G 刷入欧洲版MIU + Magisk + 信任用户证书可以使用 Charles 抓包](https://gist.github.com/wych42/b924d91d281ca1daa33d021bb45ab742)： 刷机流程，但MiUnlockTool解锁bootloader，报错提示"invalid token"(20200914)，还是要用windows和去小米官网下载工具

[Redmi note 8 pro : cant boot in recovery mode](https://www.reddit.com/r/Xiaomi/comments/dhdmra/redmi_note_8_pro_cant_boot_in_recovery_mode/): **Just to make sure: First press volume up then power button. Then release power button when phone restarts and keep holding volume up for a few seconds.**

[Redmi Note 8 Pro – Global Stable ROM Version List](https://mirom.ezbox.idv.tw/en/phone/begonia/roms-global-stable/): 因为没有（据说更干净的）EU版，[以后也不会有](https://xiaomi.eu/community/threads/xiaomi-eu-hmnote8pro-mtk-begonia-support.53542/)

[magisk-mipay-lmi](https://github.com/rewqazxv/magisk-mipay-lmi)：本仓库`update-binary`和目录结构都是从这里抄的


