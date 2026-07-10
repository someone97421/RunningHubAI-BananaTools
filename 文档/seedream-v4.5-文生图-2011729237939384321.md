# seedream-v4.5-文生图

- 官方详情页：[https://www.runninghub.ai/call-api/api-detail/2011729237939384321](https://www.runninghub.ai/call-api/api-detail/2011729237939384321)
- 模型 ID：`2011729237939384321`
- 接口：`/seedream-v4.5/text-to-image`
- 更新时间：2026-05-25 18:45:44

## 简介

字节跳动推出的新一代超高清文生图大模型。通过大规模架构优化与训练，该模型在视觉美学与逻辑理解上实现了质的飞跃。其最显著的突破在于卓越的文字渲染与海报排版能力，能够精准呈现清晰、易读的品牌标识与市场视觉素材。无论是复杂的 UI 界面设计，还是具有严谨层级关系的商业海报，Seedream 4.5 都能提供设计师级别的构图表现。凭借对复杂提示词的高度遵循及最高 4K 的自定义分辨率输出，它已成为品牌创意与视觉设计的强力引擎。

## 模型特点

- 卓越文字渲染
- 设计师级构图
- 强力提示词遵循
- 4K超高清输出
- 品牌视觉优化
- 顶级美学表现

## 提交请求

```bash
curl --location --request POST 'https://www.runninghub.ai/openapi/v2/seedream-v4.5/text-to-image' \
  --header "Content-Type: application/json" \
  --header "Authorization: Bearer ${RUNNINGHUB_API_KEY}" \
  --data-raw '{
  "prompt": "一张极具电影感的武侠海报，夜雨中的悬崖古寺，一位白衣侠客背对镜头立于断桥边缘，长发与衣袂在风中翻飞，手中长剑滴血，远处雷光映照出追兵剪影。背景是云雾缭绕的群山与倾塌的佛塔，氛围悲壮而诗意。海报顶部中央以苍劲金色书法大字呈现电影标题《孤鸿》；底部三分之一处为半透明黑色横条，内含白色宋体小字演职员表：“导演：林无尘｜主演：沈青崖、白九娘｜摄影：江月明｜出品：江湖影业”。整体构图遵循经典电影海报比例，文字排版精准、不遮挡主体人物，电影级光影、高对比度、2K 细节。",
  "width": 2048,
  "height": 2048,
  "sequentialImageGeneration": "disabled",
  "maxImages": 1
}'
```

## 请求参数

| 参数 | 类型 | 是否必填 | 说明 |
|---|---|---|---|
| `prompt` | String | 必填 | prompt；文本长度：5–2000；默认值：一张极具电影感的武侠海报，夜雨中的悬崖古寺，一位白衣侠客背对镜头立于断桥边缘，长发与衣袂在风中翻飞，手中长剑滴血，远处雷光映照出追兵剪影。背景是云雾缭绕的群山与倾塌的佛塔，氛围悲壮而诗意。海报顶部中央以苍劲金色书法大字呈现电影标题《孤鸿》；底部三分之一处为半透明黑色横条，内含白色宋体小字演职员表：“导演：林无尘｜主演：沈青崖、白九娘｜摄影：江月明｜出品：江湖影业”。整体构图遵循经典电影海报比例，文字排版精准、不遮挡主体人物，电影级光影、高对比度、2K 细节。 |
| `width` | Int | 可选 | width；范围：512–8192；步长：8；默认值：2048 |
| `height` | Int | 可选 | height；范围：512–8192；步长：8；默认值：2048 |
| `sequentialImageGeneration` | String | 可选 | sequentialImageGeneration；枚举：disabled, auto；默认值：disabled |
| `maxImages` | Int | 可选 | maxImages；范围：1–15；步长：1；默认值：1 |
| `resolution` | String | 可选 | 优先级高于widthxheight，传递resolution则使用resolution，不再使用widthxheight；枚举：2k, 4k |
| `webhookUrl` | String | 可选 | 任务完成时接收 POST 回调的地址 |

## 提交响应示例

```json
{
  "taskId": "2013508786110730241",
  "status": "RUNNING",
  "errorCode": "",
  "errorMessage": "",
  "results": null
}
```

## 查询结果

```bash
curl --location --request POST 'https://www.runninghub.ai/openapi/v2/query' \
  --header "Content-Type: application/json" \
  --header "Authorization: Bearer ${RUNNINGHUB_API_KEY}" \
  --data-raw '{"taskId":"${RUNNINGHUB_TASKID}"}'
```

常见状态：`QUEUED`、`RUNNING`、`SUCCESS`、`FAILED`。结果位于 `results`，其中 `url` 通常仅在 24 小时内有效，应及时下载或转存。

## 文件上传

媒体参数可使用公共 URL、Base64 data URI，或先上传本地文件：

```bash
curl --location --request POST 'https://www.runninghub.ai/openapi/v2/media/upload/binary' \
  --header "Authorization: Bearer ${RUNNINGHUB_API_KEY}" \
  --form "file=@/path/to/input.png"
```

上传链接有效期通常为 1 天。
