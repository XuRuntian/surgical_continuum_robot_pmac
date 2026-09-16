# surgical_continuum_robot_pmac

Power PMAC 五轴连续体机器人控制工程。

2026-09-08 的通信修复需要与 `robo-pmac-driver` 的协议 v2 配套使用，重新构建并下载全局定义、库、PLC 2/3/4 和 prog 1。Python/PLC 混用旧版本会拒绝启动或提交。寄存器地址和验证说明见配套驱动的 `docs/pmac_protocol_v2.md`。

PLC 4 复位现在停在“反馈可用、PVT 尚未启动”的状态，Python 取得新的位置快照后才启动 prog 1。PLC 1 的启用状态和机械标定保持原设置。

本次没有修改 PLC 1 的限位与恢复点。其恢复目标仍在限位外，按调试约定另行处理；本次离线测试不代表 PLC 编译和硬件验证已经完成。
