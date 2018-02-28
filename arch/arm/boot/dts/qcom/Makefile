
dtb-$(CONFIG_ARCH_SDXPOORWILLS) += sdxpoorwills-rumi.dtb \
	sdxpoorwills-cdp.dtb \
	sdxpoorwills-mtp.dtb \
	sdxpoorwills-atp.dtb \
	sdxpoorwills-ttp.dtb \
	sdxpoorwills-cdp-256.dtb \
	sdxpoorwills-mtp-256.dtb \
	sdxpoorwills-dualwifi-cdp.dtb \
	sdxpoorwills-dualwifi-mtp.dtb \
	sdxpoorwills-pcie-ep-cdp-256.dtb \
	sdxpoorwills-pcie-ep-mtp-256.dtb \
	sdxpoorwills-pcie-ep-cdp.dtb \
	sdxpoorwills-pcie-ep-mtp.dtb \
	sdxpoorwills-v2-mtp.dtb \
	sdxpoorwills-v2-cdp.dtb

dtb-$(CONFIG_ARCH_MDM9650) += mdm9650-nand-mtp.dtb \
	mdm9650-ttp.dtb \
	mdm9650-v1.1-nand-mtp.dtb \
	mdm9650-v1.1-nand-cv2x.dtb

dtb-$(CONFIG_ARCH_MDM9607) += mdm9607-mtp.dtb \
	mdm9607-ttp.dtb

ifeq ($(CONFIG_MACH_XIAOMI_MSM8940),y)
dtb-$(CONFIG_MACH_XIAOMI_SANTONI) += msm8940-pmi8950-qrd-sku7.dtb
else
dtb-$(CONFIG_ARCH_MSM8940) += msm8940-pmi8937-cdp.dtb \
	msm8940-pmi8937-mtp.dtb \
	msm8940-pmi8950-cdp.dtb \
	msm8940-pmi8950-mtp.dtb \
	msm8940-pmi8937-rcm.dtb \
	msm8940-pmi8950-rcm.dtb \
	msm8940-pmi8950-qrd-sku6.dtb \
	msm8940-pmi8950-qrd-sku7.dtb \
	msm8940-pmi8950-ext-codec-cdp.dtb \
	msm8940-pmi8940-mtp.dtb \
	msm8940-pmi8940-cdp.dtb \
	msm8940-pmi8940-rcm.dtb \
	msm8940-pmi8940-qrd-sku7.dtb
endif

dtb-$(CONFIG_ARCH_MSM8953) += msm8953-sim.dtb \
	msm8953-rumi.dtb \
	msm8953-cdp.dtb \
	msm8953-mtp.dtb \
	msm8953-ext-codec-mtp.dtb \
	msm8953-qrd-sku3.dtb \
	msm8953-rcm.dtb \
	apq8053-rcm.dtb \
	msm8953-ext-codec-rcm.dtb \
	apq8053-cdp.dtb \
	apq8053-ipc.dtb \
	msm8953-ipc.dtb \
	apq8053-mtp.dtb \
	apq8053-ext-audio-mtp.dtb \
	apq8053-ext-codec-rcm.dtb \
	msm8953-cdp-1200p.dtb \
	msm8953-iot-mtp.dtb \
	apq8053-iot-mtp.dtb \
	msm8953-pmi8940-cdp.dtb \
	msm8953-pmi8940-mtp.dtb \
	msm8953-pmi8937-cdp.dtb \
	msm8953-pmi8937-mtp.dtb \
	msm8953-pmi8940-ext-codec-mtp.dtb \
	msm8953-pmi8937-ext-codec-mtp.dtb

dtb-$(CONFIG_ARCH_SDM450) += sdm450-rcm.dtb \
	sdm450-cdp.dtb \
	sdm450-mtp.dtb \
	sdm450-qrd.dtb \
	sdm450-pmi8940-mtp.dtb \
	sdm450-pmi8937-mtp.dtb \
	sdm450-iot-mtp.dtb \
	sda450-cdp.dtb \
	sda450-mtp.dtb

dtb-$(CONFIG_ARCH_MDM9607) += mdm9607-rumi.dtb \
	mdm9607-cdp.dtb \
	mdm9607-mtp.dtb \
	mdm9607-rcm.dtb \
	mdm9607-mtp-sdcard.dtb \
	mdm9607-ttp.dtb \
	mdm9206-mtp.dtb \
	mdm9206-cdp.dtb \
	mdm9206-mtp-sdcard.dtb \
	mdm9206-rcm.dtb

include $(srctree)/arch/arm64/boot/dts/qcom/Makefile
$(obj)/%.dtb: $(src)/../../../../arm64/boot/dts/qcom/%.dts FORCE
	$(call if_changed_dep,dtc)

ifeq ($(CONFIG_ARM64),y)
always          := $(dtb-y)
subdir-y        := $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/%.dtbo:$(src)/../../../../arm64/boot/dts/qcom/%.dts FORCE
	$(call if_changed_dep,dtc)
	$(call if_changed,dtbo_verify)

endif
clean-files := *.dtb
