# GetPasswordPolicy {#doc_api_Ram_GetPasswordPolicy .reference}

获取子用户密码强度等策略。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Ram&api=GetPasswordPolicy)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|GetPasswordPolicy|系统规定参数。取值：GetPasswordPolicy

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PasswordPolicy| | |密码策略。

 |
|└HardExpiry|Boolean|false|密码是否过期。

 取值为`true`或`false`，如果未指定此参数的值，系统默认为`false`。

 -   如果取值为`true`，此时必须由主账号重置密码后，RAM用户才能正常登录。
-   如果取值为`false`，此时RAM用户可以在密码过期后自行更改密码，并继续以用户身份登录。

 |
|└MaxLoginAttemps|Integer|5|一小时内使用错误密码尝试登录最大次数（重置密码可清除尝试登录计数）。

 |
|└MaxPasswordAge|Integer|0|密码有效期，单位是天（重置密码将重置密码过期时间）。0表示不启用密码过期策略，默认不启用。

 |
|└MinimumPasswordLength|Integer|12|最小密码长度。

 |
|└PasswordReusePrevention|Integer|0|禁止使用前N次密码。0表示不启用历史密码检查策略，默认不启用。

 |
|└RequireLowercaseCharacters|Boolean|true|必须包含小写字母。

 |
|└RequireNumbers|Boolean|true|必须包含数字。

 |
|└RequireSymbols|Boolean|true|必须包含字符。

 |
|└RequireUppercaseCharacters|Boolean|true|必须包含大写字母。

 |
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ram.aliyuncs.com/?Action=GetPasswordPolicy
&AcccountAlias=myalias
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<GetPasswordPolicyResponse>
  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
  <PasswordPolicy>
    <HardExpiry>false</HardExpiry>
    <MaxLoginAttemps>5</MaxLoginAttemps>
    <MaxPasswordAge>0</MaxPasswordAge>
    <PasswordReusePrevention>0</PasswordReusePrevention>
    <MinimumPasswordLength>12</MinimumPasswordLength>
    <RequireLowercaseCharacters>true</RequireLowercaseCharacters>
    <RequireUppercaseCharacters>true</RequireUppercaseCharacters>
    <RequireNumbers>true</RequireNumbers>
    <RequireSymbols>true</RequireSymbols>
  </PasswordPolicy>
</GetPasswordPolicyResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368",
	"PasswordPolicy":{
		"RequireUppercaseCharacters":true,
		"MaxPasswordAge":0,
		"HardExpiry":false,
		"RequireNumbers":true,
		"RequireSymbols":true,
		"MaxLoginAttemps":5,
		"PasswordReusePrevention":0,
		"RequireLowercaseCharacters":true,
		"MinimumPasswordLength":12
	}
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Ram)

