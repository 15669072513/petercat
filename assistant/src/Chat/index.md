---
atomId: Chat
---

# Chat

Chat 是一个基于 @ant-design/pro-chat 和 @ant-design/pro-editor 构建的聊天组件，提供了丰富的功能和配置选项。它支持与一个基于 API 的聊天服务进行交互，并且可以渲染多种消息类型。

## 安装

确保你已经安装了必要的依赖：

```bash
npm install @petercatai/assistant
```

## 使用示例


```jsx
import React, { useEffect, useState } from 'react';
import { Chat } from '@petercatai/assistant';

export default () => {
  const [res, setRes] = useState({});

  useEffect(() => {
    console.log('res', res);
  }, [res]);
  const meta = {
      avatar: `https://mdn.alipayobjects.com/huamei_bfc7ch/afts/img/A*allUQLXaWmYAAAAAAAAAAAAADst8AQ/original`,
      title: 'AI助手',
  }
  return (
    <div style={{ height: '100vh' }}>
      <Chat
        disabled={false}
        helloMessage={"您好！感谢您的热情和支持！作为阿里巴巴云的AI助手Qwen，我的目标是尽可能地为您提供帮助和服务。您可以向我提出各种问题或需求，比如： 1. **技术咨询**：如果您在使用阿里云的产品或服务时遇到技术难题，或者想了解最新的技术趋势，都可以随时询问。 2. **产品使用指导**：对于阿里云的各种产品，如ECS、RDS等，如果您需要详细的使用指南或操作建议，我也很乐意提供帮助。 3. **创意灵感**：如果您正在寻找新的业务想法或是想要提升现有项目的创新点，我们可以一起探讨，激发更多可能性。 4. **行业资讯**：如果您对特定行业的最新动态感兴趣，例如云计算、人工智能等领域的发展情况，我可以帮您搜集相关信息。 无论您的需求是什么，只要是我能力范围内的，我都会尽全力协助。期待能够成为您值得信赖的伙伴，共同成长进步！如果有具体的需求，请随时告诉我哦。😊"}
        disabledPlaceholder="`机器人尚未配置任何内容 ,请在完成配置后进行对话测试`"
        starters={[
          '介绍下xxx这个项目',
          '查看xxx的贡献指南',
          '我该怎样快速上手',
        ]}
        apiUrl="/api/chat/stream_qa"
        hideLogo="true"
        getToolsResult={setRes}
        assistantMeta={meta}
      />
    </div>
  );
};
```

## API

| 属性名 | 类型 | 默认值 | 描述 |
| --- | --- | --- | --- |
| `apiDomain` | `string` | `'http://api.petercat.ai'` | API 域名地址，组件将通过此域名与后端服务进行通信。 |
| `apiUrl` | `string` | `undefined` | 指定聊天 API 的 URL 路径，如果未指定，将使用默认路径。 |
| `drawerWidth` | `number` | `500` | 控制聊天窗口的宽度。 |
| `assistantMeta` | `MetaData` | `{}` | 设置聊天助手的元数据信息，包括头像、标题和背景颜色。 |
| `helloMessage` | `string` | `undefined` | 设定聊天窗口打开时的欢迎消息。 |
| `starters` | `string[]` | `[]` | 聊天启动器消息的数组，用户可以选择这些消息来快速开始对话。 |
| `prompt` | `string` | `undefined` | 指定聊天的提示内容，用于指导对话的进行。 |
| `token` | `string` | `undefined` | 用于验证聊天服务的令牌。 |
| `style` | `React.CSSProperties` | `{}` | 自定义聊天组件的内联样式。 |
| `hideLogo` | `boolean` | `false` | 是否隐藏聊天窗口顶部的 Logo。 |
| `disabled` | `boolean` | `false` | 是否禁用聊天输入区域，禁用后用户无法输入消息。 |
| `disabledPlaceholder` | `string` | `undefined` | 当聊天输入区域被禁用时显示的占位符文本。 |
| `getToolsResult` | `(response: any) => void` | `undefined` | 用于接收工具处理结果的回调函数。 |
