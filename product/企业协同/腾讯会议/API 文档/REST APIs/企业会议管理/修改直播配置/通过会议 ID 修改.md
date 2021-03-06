
## 接口描述
描述：通过会议 ID 修改直播配置信息。
调用方式：PUT
接口请求域名：`https://api.meeting.qq.com/v1/meetings/${meeting_id}/live_play/config`

 
## 输入参数
HTTP 请求头公共参数参考签名验证章节里的 [公共参数说明](https://cloud.tencent.com/document/product/1095/42413#.E5.85.AC.E5.85.B1.E5.8F.82.E6.95.B0)。

| 参数名称    | 必选 | 参数类型 | 参数描述           |
| ----------- | ---- | -------- | ------------------ |
| userid      | 是   | String   | 用户 ID。            |
| instanceid  | 是   | integer  | 用户的终端设备类型。 |
| live_config | 是   | Object   | 直播配置。           |

## 输出参数
无输出参数，则成功返回空消息体，失败返回错误码和错误信息。

| 参数名称   | 必选 | 参数类型 | 参数描述                 |
| ---------- | ---- | -------- | ------------------------ |
| error_info | 否   | Object   | 错误信息对象（失败时返回）。 |

## 错误信息对象定义

| 参数名称   | 参数类型 | 参数描述 |
| ---------- | -------- | -------- |
| error_code | Integer  | 错误码。   |
| message    | String   | 错误描述。 |


## 直播配置对象

| 参数名称             | 参数类型 | 参数描述         |
| -------------------- | -------- | ---------------- |
| live_subject         | String   | 直播主题。         |
| live_summary         | String   | 直播简介。         |
| enable_live_password | String   | 是否开启直播密码。 |
| live_password        | string   | 直播密码。         |
| enable_live_im       | Boolean  | 是否开启直播互动。 |
| enable_live_replay   | Integer  | 是否开启直播回放。 |


## 示例
#### 输入示例
```
PUT https://api.meeting.qq.com/v1/meetings/${meeting_id}/live_play/config

{
    "userid": "test_userid",
    "instanceid": 1,
    "live_config": {
   	 "live_subject": "test_subject",
   	 "live_summary": "test_summary",
   	 "enable_live_password": true,
   	 "live_password": "654321",
   	 "enable_live_im": true,
   	 "enable_live_replay": true
    }
}
```

#### 输出示例（失败时返回）
```
{"error_info":{"error_code":200005,"message":"Json Schema validation failed!"}}
```
