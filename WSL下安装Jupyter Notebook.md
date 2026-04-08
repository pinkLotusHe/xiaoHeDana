# 第一步：在windows11上安装 WSL

1. 打开 PowerShell
点击开始菜单，搜索“PowerShell”，选择“以管理员身份运行”。

2. 一键安装 WSL
    在管理员 PowerShell 窗口，输入：
    ```
        wsl --install
        或
        wsl.exe --install
    ```
    这条命令会自动完成以下操作：
    
    - 启用 Windows 的“适用于 Linux 的 Windows 子系统”和“虚拟机平台”功能
    - 下载并安装最新的 Linux 内核
    - 安装默认的 Linux 发行版
    
    如果出现下面的情况也没关系
    <img width="1919" height="197" alt="image" src="https://github.com/user-attachments/assets/e3b17eea-4ac9-437e-ad74-d2bf3ca17319" />

    
    输入下面的两个命令
    ```
        dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
        dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    ```
    
    <img width="1065" height="369" alt="image" src="https://github.com/user-attachments/assets/2092de3c-f882-47f6-83b4-831d2ae84085" />

    
    然后重启，再执行wsl --install或wsl.exe --install
    
    执行完之后会让设置用户和输入密码，按提示操作即可
    
    <img width="1058" height="451" alt="image" src="https://github.com/user-attachments/assets/b00779ee-8580-44e7-98ad-6a5dc44d67a3" />

    
    到此就全部安装完成了，如果没有出现输入用户名和密码的情况，需要手动启动linux，按接下来的步骤操作即可

3. 验证安装是否成功


   输入下面的命令
    ```
        wsl -l -v
    ```
    <img width="1037" height="289" alt="image" src="https://github.com/user-attachments/assets/316e7ae8-a0d5-46ba-be1c-4dd60c40c401" />

5. 启动 Linux


   直接在windows 搜索框输入 `ubuntu`，打开即可。
    或在PowerShell里面输入
    ```
        wsl
        wsl -d 发行版名称
    ```
    <img width="1067" height="203" alt="image" src="https://github.com/user-attachments/assets/f384a620-b6f7-4ad1-a1cb-50a110f40ba9" />

# 第二步：在WSL上安装 Jupyter Notebook
1. 在WSL上安装python
    ```
    sudo apt update && upgrade
    sudo apt install python3 python3-pip ipython3
    ```
2. 查看python版本
    ```
    python3 --version
    ```
    <img width="1077" height="79" alt="image" src="https://github.com/user-attachments/assets/de4c0f98-2753-4d2f-9a84-e30869898680" />


3. 安装jupyter notebook
    ```
    pip3 install jupyter
    ```
    <img width="1065" height="414" alt="image" src="https://github.com/user-attachments/assets/842c9725-92bb-4637-9939-6d8a8e0d1271" />


4. 启动jupyter notebook
    ```
    jupyter notebook --no-browser --allow-root
    ```
    <img width="1076" height="477" alt="image" src="https://github.com/user-attachments/assets/a0a3aa61-b909-4438-8203-b33fce67f82b" />


5. 打开jupyter notebook网页
    把上一步生成的URL拷贝到浏览器地址栏，回车，
    <img width="1081" height="171" alt="image" src="https://github.com/user-attachments/assets/110aa28e-9450-4bdc-92fc-b895fe84367c" />

    
    即会打开jupyter notebook默认网页 `http://localhost:8888/tree`
    
    <img width="852" height="698" alt="image" src="https://github.com/user-attachments/assets/c740c287-b4cb-4cc0-bea0-182b0a208290" />
