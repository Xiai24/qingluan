QINGLUAN FLY CONTROL

---

```markdown
# 青鸾低空冷链无人机飞控系统

## 项目简介

青鸾飞控系统是专为低空冷链物流场景深度定制的开源飞控解决方案，基于 ArduPilot 框架二次开发，融合 AI 需求预测、区块链温控追溯与轻量化硬件设计，
主要为医药冷链（±0.5℃ 精准温控）提供安全、合规、低成本的无人机运输方案，同时也是赤风生鲜配送系列的控制系统。

## 核心特性

-   **冷链场景深度适配**
    -   载重自适应 PID 控制算法，保障不同负载下的飞行稳定性
    -   高精度温度传感器集成，实时监控冷链箱内部环境
    -   温控异常自动响应机制，支持应急处理策略
-   **智能协同调度**
    -   AI 预测数据接口，支持动态路径规划与优先级调度
    -   多无人机集群协同算法，优化空域资源利用
    -   中转站智能选址模型，降低整体配送成本
-   **合规性保障**
    -   区块链数据上链模块，满足 GSP 认证要求
    -   电子凭证自动生成，支持海关快速核验
    -   5 年数据留存机制，确保全程可追溯
-   **国产化低成本方案**
    -   90%国产化硬件适配，单架成本控制在 2000 元内
    -   边缘计算部署，无需依赖高成本云端基础设施
    -   开源硬件设计，支持 3D 打印与快速迭代

## 技术架构
```

![image](https://github.com/user-attachments/assets/26bf195e-7c3d-4c01-b991-6c867e9b0ae3)

````

## 快速开始
### 开发环境搭建
1. 克隆仓库
```bash
git clone https://github.com/your-organization/qingluan-firmware.git
cd qingluan-firmware
````

2. 安装依赖

```bash
# Ubuntu/Debian系统
./Tools/environment_install/install-prereqs-ubuntu.sh -y

# macOS系统
brew install git cmake ninja python3
```

3. 编译固件

```bash
# 编译适用于STM32H743的四轴飞行器固件
./waf configure --board CubeBlack
./waf copter
```

### 硬件连接

-   主控：支持 Pixhawk 4、CubeBlack 等主流飞控板
-   传感器：DS18B20 温度传感器（冷链箱内）、BME280 环境传感器、激光雷达（避障）
-   通信：4G 模块（数据回传）、UHF 电台（地面站通信）

### 首次飞行

1. 使用 QGroundControl 加载编译好的固件
2. 进行基础参数配置（飞行器类型、传感器校准）
3. 设置冷链专用参数（载重、温控阈值、应急降落点）
4. 上传包含温度监控点的任务计划
5. 启动飞行，通过地面站实时监控温度与飞行数据

## 文档与资源

-   [开发指南](docs/development_guide.md) - 详细的代码结构与开发规范
-   [硬件适配手册](docs/hardware_adaptation.md) - 支持的硬件列表与连接方式
-   [API 参考](docs/api_reference.md) - 对外接口与数据格式说明
-   [冷链场景应用案例](docs/application_cases.md) - 医药/生鲜配送实战经验分享
-   [贡献指南](CONTRIBUTING.md) - 如何参与项目开发与提交代码

## 社区支持

-   讨论区：[GitHub Discussions](https://github.com/your-organization/qingluan-firmware/discussions)
-   问题反馈：[GitHub Issues](https://github.com/your-organization/qingluan-firmware/issues)
-   邮件列表：qingluan-dev@googlegroups.com
-   微信公众号：青鸾展翼

## 开源协议

本项目采用[Apache 2.0 许可证](LICENSE)，允许自由使用、修改和分发，但需保留版权声明。商业使用请联系我们获取企业版授权。

## 贡献者

感谢所有为项目做出贡献的开发者！查看[贡献者列表](https://github.com/your-organization/qingluan-firmware/graphs/contributors)

## 鸣谢

本项目基于 ArduPilot 开源框架开发，感谢 ArduPilot 社区的贡献。同时感谢上海市科委、临港新片区管委会的支持。

## 联系我们

-   项目负责人：胡 (Hu@qingluan.tech)
-   商务合作：吉 (Ji@qingluan.tech)
-   研发中心：上海城建职业学院
