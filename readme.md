#  VolcEngine ImageX Integration for Fresns

## Feature

1. [Basic] File storage. You can save almost anything you like in ImageX
2. [Powerful] Image processing. You can change your image processing to optimize the bandwidth.
3. [Safe] Url signature. Guest can not get your file without a correct signature from your site.

## Configuration

| Section           | Configuration                   | Meaning                                                                                                             |
| ----------------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Server Config     | Service Provider                | Set to `ImageX Integration`                                                                                         |
|                   | Secret ID                       | Your access key ID get from [VolcEngine IAM](https://console.volcengine.com/iam/keymanage/)                         |
|                   | Secret Key                      | Your secret access key get from [VolcEngine IAM](https://console.volcengine.com/iam/keymanage/)                     |
|                   | Bucket Name                     | Your service ID get from [VolcEngine ImageX](https://console.volcengine.com/imagex/service_manage/)                 |
|                   | Bucket Area                     | Your service region get from [VolcEngine ImageX](https://console.volcengine.com/imagex/service_manage/) (1)         |
|                   | Bucket Domain Name              | Your service domain set in [VolcEngine ImageX](https://console.volcengine.com/imagex/service_manage/)               |
|                   | Filesystem Disk                 | Set to `remote`                                                                                                     |
| Function Config   | Anti Link Key                   | Your url signature secret (2)                                                                                       |
|                   | Valid minutes for sign          | Keep the value less then the value set in the page `Anti Link Key` mentioned.                                       |
| Image Function    | Image Handle Position           | Set to suffix padding                                                                                               |
|                   | Any other blank in this section | Starts with `~tplv-`, ends with file extension name                                                                 |
| Video Function    | `WIP`                           | `WIP`                                                                                                               |
| Audio Function    | `-`                             | `Not supported`. ImageX does't provide any audio processing funcion. But you can storage your audio file in ImageX. |
| Document Function | `-`                             | `Supported`. ImageX can storage any file you like.                                                                  |


(1) The value is properly one of `cn-north-1`, `ap-singapore-1`, `us-east-1`

(2) Configuration page `https://console.volcengine.com/imagex/service_manage/http_config/{SERVICE_ID}/{DOMAIN}`, e.g. `https://console.volcengine.com/imagex/service_manage/http_config/dQw4w9WgXcQ/example.com`. This plugin only supports method B.
