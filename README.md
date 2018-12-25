Ubuntu
你可以在你的 Ubuntu 系统中添加我们的 APT 仓库，这样就可以便于未来安装或更新我们的软件包（通过 apt-get update 命令）。 运行下面的命令就可以添加仓库（每个系统只需要运行一次）：

    # 导入我们的 GPG 密钥：
    wget -qO - https://openresty.org/package/pubkey.gpg | sudo apt-key add -

    # 安装 add-apt-repository 命令
    # （之后你可以删除这个包以及对应的关联包）
    sudo apt-get -y install software-properties-common

    # 添加我们官方 official APT 仓库：
    sudo add-apt-repository -y "deb http://openresty.org/package/ubuntu $(lsb_release -sc) main"

    # 更新 APT 索引：
    sudo apt-get update
然后就可以像下面这样安装软件包，比如 openresty：

    sudo apt-get install openresty
