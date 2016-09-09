# Custom kernel for Xiaomi Redmi Note 2 (Hermes)
# Kernel version 3.10.72
# Vendor Vanzo (ALPS-MP-M0.MP11-V1_VZ6795_LWT_M)
Works in rom(ALPS 6.0)

* Works:
	* LCM(nt35596 tianma , nt35596_auo , nt35532_boe)
	* Touch (atmel , ft5206)
	* CW2015
	* Sdcard
	* Wi-fi
	* BT
	* GPS
	* Button-backlight
	* Brightness
	* Leds indication
	* Rill(sim1 and sim2)
	* Alsps (LT559)
	* Accel(BMI160_acc)
	* Mag
	* Giro
	* OTG
	* SOUND(Speaker,Headphones)
	* Vibrator
	* Battery 3000mah(stock table)
	* Flashlight
	* CAMERA(s5k3m2 OV5670)
	* Lens(DF9761BAF)
	* Fixed graphics bug
      	* Fixed bug headphones Disconnects
      	* 
* Don't work:
	* IR Blaster

=================================================
# BUILD
export TOP=$(pwd)
export CROSS_COMPILE=/home/nofearnohappy/aarch64-linux-android-4.9-linaro-master/bin/aarch64-linux-android-
mkdir -p $TOP/KERNEL_OBJ
make -C kernel-3.10 O=$TOP/KERNEL_OBJ ARCH=arm64 MTK_TARGET_PROJECT=vz6795_lwt_m TARGET_BUILD_VARIANT=user CROSS_COMPILE=$TOOLCHAIN ROOTDIR=$TOP vz6795_lwt_m_defconfig
make -C kernel-3.10 O=$TOP/KERNEL_OBJ ROOTDIR=$TOP

# I2C

* I2C0
	* tps65132              (003e)
	* kd_camera_hw          (007f)
	* DF9761BAF             (0018) - LENS
	* CAM_CAL_DRV           (0036)

* I2C1
	* da9210                (0068)
	* tps6128x              (0075)

* I2C2
	* atmel                 (004a)
	* kd_camera_hw_bus 2    (007f)
	* FT			(0038)

* I2C3
	* akm0991               (000c)
	* yas537                (002e)
	* LSM6DS3_ACCEL         (006a)
	* LTR_559ALS		(0023)
	* LSM6DS3_GYRO		(0034)
	* stk3x1x               (0048)
	* bmi160_gyro		(0066)
	* bmi160_acc		(0068)

* I2C4
	* CW2015 		(0062)

# AUTORS
* nofearnohappy
* LazyC0DEr
* Anomalchik
