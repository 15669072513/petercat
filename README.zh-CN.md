

## 🚀 快速上手

首先，克隆这个仓库。
接下来，需要在仓库的 .env.local 文件中设置环境变量：复制 .env.example 文件到 .env.local，添加你的 OpenAI API 密钥。
接下来，使用您喜欢的包管理器（例如 yarn）安装所需的包。
现在你可以运行开发服务器了：

```bash 
# node version: >=18
yarn install
yarn dev
```

用你的浏览器打开 [http://localhost:3000](http://localhost:3000) 就能看到以下页面：
![A streaming conversation between the user and the AI](/public/images/chat-conversation.png)

你可以开始修改页面从 `app/page.tsx` 开始. 页面会自动更新。

后端逻辑位于 `app/api/chat/route.ts`。在这里，你可以更改提示和模型，或者添加其他模块和逻辑。


