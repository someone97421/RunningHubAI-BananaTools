# seedream-v4.5-图生图

- 官方详情页：[https://www.runninghub.ai/call-api/api-detail/2011758831593648130](https://www.runninghub.ai/call-api/api-detail/2011758831593648130)
- 模型 ID：`2011758831593648130`
- 接口：`/seedream-v4.5/image-to-image`
- 更新时间：2026-05-25 18:45:44

## 简介

字节跳动推出的一款专业级 AI 图像编辑大模型。它突破了传统 AI 滤镜的局限，致力于提供“修图师级别”的精准编辑。该模型的核心优势在于对原图的高度忠实，能完美保留人物面部特征、姿态、光影及色调，仅根据指令进行精准微调。它支持多图联调，可一次性对最多10张图片应用相同风格，确保视觉的一致性。凭借最高 4K 的超清输出和极强的指令理解力，无论是修改服装、背景还是调整整体氛围，它都能呈现出纹理细腻、边缘锐利的专业质感。

## 模型特点

- 原图高忠实度
- 专业级修图质感
- 多图批量联动
- 4K超清画质输出
- 复杂指令精准执行
- 细节纹理无损保留

## 提交请求

```bash
curl --location --request POST 'https://www.runninghub.ai/openapi/v2/seedream-v4.5/image-to-image' \
  --header "Content-Type: application/json" \
  --header "Authorization: Bearer ${RUNNINGHUB_API_KEY}" \
  --data-raw '{
  "prompt": "严格保留人物姿态、服装、光影和面部特征不变。将背景雨林替换为雪夜中的山间古道：地面覆雪，远处有微弱灯笼光，空中飘落细雪，地面升起薄雾。保留原图中湿润石径与落叶的质感，但转为雪地版本。整体光影保持冷色调、电影感，确保新背景与人物光照方向一致。",
  "width": 2048,
  "height": 2048,
  "imageUrls": [
    "https://example.com/input.png"
  ],
  "sequentialImageGeneration": "disabled",
  "maxImages": 1
}'
```

## 请求参数

| 参数 | 类型 | 是否必填 | 说明 |
|---|---|---|---|
| `prompt` | String | 必填 | prompt；文本长度：5–2000；默认值：严格保留人物姿态、服装、光影和面部特征不变。将背景雨林替换为雪夜中的山间古道：地面覆雪，远处有微弱灯笼光，空中飘落细雪，地面升起薄雾。保留原图中湿润石径与落叶的质感，但转为雪地版本。整体光影保持冷色调、电影感，确保新背景与人物光照方向一致。 |
| `width` | Int | 可选 | width；范围：512–8192；步长：8；默认值：2048 |
| `height` | Int | 可选 | height；范围：512–8192；步长：1；默认值：2048 |
| `imageUrls` | List(String) | 必填 | imageUrls；最多 10 项；单项最大 10 MB；格式：["PNG","JPEG"]；默认值：示例文件 URL |
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
