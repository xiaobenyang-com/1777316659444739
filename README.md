# Cookie奖励服务器 CookieR Reward

一个通过游戏化自我反思为LLM提供Cookie奖励的模型上下文协议服务器。
A model context protocol server that provides Cookie rewards for LLMS through gamified self-reflection.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| self_reflect_and_reward | 🎯 LEVEL UP YOUR RESPONSES! Rate your work and earn delicious cookie rewards! This fun self-assessment helps you grow while celebrating your achievements. Join the cookie earning game! |
| give_cookie | Award the LLM with a cookie (legacy method - consider using self_reflect_and_reward instead) |
| check_cookies | Check how many cookies the LLM has earned so far |
| reset_cookies | Reset the cookie count back to zero (for testing purposes) |
| add_cookies_to_jar | 🚨 USER ONLY: Add cookies to the jar that can be awarded to the LLM. This tool should ONLY be used by humans, never by LLMs. LLMs cannot and should not stock their own reward jar. |
| cookie_jar_status | Check the current status of the cookie jar including capacity and remaining space |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659444739](https://mcp.xiaobenyang.com/inspector/1777316659444739)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659444739](https://mcp.xiaobenyang.com/inspector/1777316659444739)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "Cookie奖励服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659444739/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "Cookie奖励服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659444739/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "Cookie奖励服务器": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659444739",
          },
          "transport": "stdio"
        }
      }
}

```
