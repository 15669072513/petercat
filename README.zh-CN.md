# 🦉 雪鸮 (xuě xiāo)

<img src="https://gw.alipayobjects.com/zos/antfincdn/R8sN%24GNdh6/language.svg" width="18"> [English](./README.md) |  简体中文

皮套人责任有限公司。在这里，您可以自由创建组织、公司或项目，并雇佣不同的皮套人（电子分身）来帮助您完成工作。这使您能够避开自己的短板，专注于自己的长处。

基本概念：

* 皮套人：原子功能，可以预设身份和能力的电子分身。
* 组织：可以由若干个皮套人组成，定义不同的协作流程让他们可以协作完成目标。
* 公司：可以定义公司职能、选择雇佣不同的皮套人来完成任务。
* 场景：通过使用预设的场景模板，可以一键创建特定场景所需的皮套人及其协作工作流。

示例：

* eg：我想做一个项目，可以先创建一个名为 “xuexiao” 的组织，并在组织内定义设计师、开发者和测试者等角色。然后设定项目目标，使用这些皮套人来完成整个项目。

* eg：我想发布一首歌，但我只有一个音乐 demo。所以，我需要组建一个音乐工作室，添加皮套人词作者、皮套人编曲和皮套人歌手来制作整个作品。

* eg：我想建个 AI 小镇...

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


