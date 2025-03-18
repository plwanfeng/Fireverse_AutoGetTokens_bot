# Fireverse自动化工具使用指南
## 简介
Fireverse自动化工具是一个帮助用户自动获取Fireverse平台token并进行音乐播放任务的工具，可以帮助用户完成日常任务并获取积分和经验值。

## 准备工作
下载本项目

```
git clone https://github.com/plwanfeng/Fireverse_AutoGetTokens_bot.git
```

1. 安装依赖
   
   在使用前，请确保已安装所有必要的依赖包：
   
   ```bash
   npm install axios ethers fs path readline
    ```
2. 准备钱包私钥
   
   在项目根目录创建 wallets.txt 文件，每行添加一个私钥（以0x开头）：
   
   ```plaintext
   0x123456789abcdef...
   0x987654321fedcba...
    ```
## 使用方法
1. 运行程序
   
   在命令行中执行：
   
   ```bash
   node new_index.js
    ```
2. 选择是否更新Token
   
   程序启动后，会询问是否需要更新Token：
   
   - 输入 y ：程序将使用wallets.txt中的私钥获取新的token
   - 输入 n 或直接回车：程序将使用现有的tokens.txt中的token
3. 输入邀请码
   
   如果选择更新Token，程序会提示输入邀请码，默认为"wanfeng"。您可以直接按回车使用默认邀请码，或输入其他有效邀请码。
4. 自动化流程
   
   程序会自动执行以下操作：
   
   - 从wallets.txt读取私钥（如果选择更新Token）
   - 为每个私钥获取token并保存到tokens.txt（如果选择更新Token）
   - 使用获取的token创建音乐机器人
   - 自动播放音乐、点赞、评论
   - 完成每日任务，获取积分和经验值
## 功能特点
- 自动获取Token : 使用私钥自动获取并更新Fireverse平台的访问token
- 多账号支持 : 可同时运行多个账号，提高效率
- 自动播放音乐 : 自动选择推荐歌曲进行播放
- 互动功能 : 自动为歌曲点赞和评论
- 任务追踪 : 显示每日任务完成进度
- 心跳机制 : 保持在线状态，确保收听时间正确记录
- 24小时循环 : 达到每日限制后自动等待并重置
## 注意事项
1. 请确保您的网络连接稳定
2. 不要频繁重启程序，以免被平台检测为异常行为
3. 私钥信息敏感，请妥善保管wallets.txt文件
4. 每个账号每天最多可播放50首歌曲
5. 程序会自动处理错误并尝试继续运行
