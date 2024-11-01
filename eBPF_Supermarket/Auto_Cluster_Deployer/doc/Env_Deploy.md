# 环境搭建与项目部署
## 1. rust 语言编译环境安装
**此项目的数据传输使用 `rust` 语言编写，使用前需要安装 `rust` 语言的编译环境**
   ```bash
   # 安装前先配置国内镜像源，可以加速下载
   # 设置环境变量 RUSTUP_DIST_SERVER （用于更新 toolchain）：
   export RUSTUP_DIST_SERVER=https://mirrors.ustc.edu.cn/rust-static
   # RUSTUP_UPDATE_ROOT （用于更新 rustup）：
   export RUSTUP_UPDATE_ROOT=https://mirrors.ustc.edu.cn/rust-static/rustup

   # 安装 https://www.rust-lang.org/tools/install
   # 请不要使用Ubuntu的安装命令: sudo apt install cargo，否则可能会出现莫名其妙的问题
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

   # 修改 ~/.cargo/config 文件，配置 rust 使用的国内镜像源
   [source.crates-io]
   registry = "https://github.com/rust-lang/crates.io-index"
   replace-with = 'ustc'

   [source.ustc]
   registry = "git://mirrors.ustc.edu.cn/crates.io-index"
   ```
## 2. tonic执行方法
- 服务器端在`lmp/eBPF_Supermarket/Auto_Cluster_Deployer/tonic/server_tonic`路径下运行`cargo run --bin grpc-web-server`，就可以启动。
- 客户端在`lmp/eBPF_Supermarket/Auto_Cluster_Deployer/tonic/server_tonic`路径下运行`cargo run --bin grpc-web-server`，即可连接到服务器的ip。

## 3. 数据库环境部署
数据库环境部署见数据库设计文档：[db_design.md](lmp/eBPF_Supermarket/Auto_Cluster_Deployer/doc/db_design.md)
