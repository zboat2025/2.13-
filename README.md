HM213 AIOPRO 212x104 1bpp 时钟字体 · .img 打包
来源: inkclock/fonts2/  (python3 gen2.py && python3 to_img.py)
================================================================
【可刷写整机固件】73580 B，与原厂固件同尺寸，容器 CRC32 已重算
  fw_pixel_40x64.img          像素点阵 40x64，风格 0/1/3 全部替换   ★推荐
  fw_pixel_40x64_style0.img   只替换风格 0（实心粗体），风格 1/3 保留原样
  fw_sans_40x64.img           重黑体/手环风 40x64，风格 0/1/3
  fw_sans_40x64_style0.img    只替换风格 0
  deep.img                    等同于 fw_pixel_40x64.img（别名副本）

【字模容器 · 不可刷写】0x40 容器头 + 字模 payload(=同名字模 .bin)，不含代码
  pixel_30x56.img  pixel_40x56.img  pixel_40x64.img
  sans_40x56.img   sans_40x64.img

【固件字体对象布局】(tools/patch_font.py 已验证)
  字体对象头 4 B: b'0', u8 w=40, u8 h=64, u8 count=10
  随后 10 个字形 × (64 行 × 5 B) = 3200 B，行优先、MSB 在左、1=上墨
  风格 0 实心 @0x00F8AE · 风格 1 描边 @0x00D5B8 · 风格 3 装饰 @0x00EBD6
  （风格 2 @0x00E23C 是空表，未改动）
  注意：固件字库只有 0-9 十个字形，冒号由绘制代码单独画点。

【刷写步骤】
  1) 手机蓝牙开启、标签在附近、电量充足
  2) 打开「签变时光」→ 下滑到「固件升级」
  3) 选择解压后的 fw_pixel_40x64.img（在 Download/DSHA 下）
  4) 确认升级，等待写入完成，勿锁屏/离开
  5) 回滚：重新上传原厂 
