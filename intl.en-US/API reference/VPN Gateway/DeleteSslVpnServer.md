# DeleteSslVpnServer {#reference_i4w_xmt_ndb .reference}

Deletes an SSL-VPN server.

## Debug {#section_x3j_nfy_5gb .section}

By using [API Explorer](https://api.aliyun.com/#product=Vpc&api=DescribeVpcAttribute), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#section_cch_pjg_mdb .section}

|Parameter|Type|Required?|Example value|Description|
|:--------|:---|:--------|-------------|:----------|
|Action|String|Yes|DeleteSslVpnServer| The name of this action. Value:

 DeleteSslVpnServer

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the SSL-VPN server belongs.

 To query the region ID, call DescribeRegions.

 |
|SslVpnServerId|String|Yes|vss-bp18q7hzj6largv4vk2fe| The ID of the SSL-VPN server.

 |
|ClientToken|String|No|02fb3da4-130e-11e9-8e44-0016e04115b| A client token used to guarantee the idempotence of requests.

 This parameter value is generated by the client and must be unique. It must be 1 to 64 ASCII characters in length.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Parameter|Type|Example value|Description|
|:--------|:---|-------------|:----------|
|RequestId|String|606998F0-B94D-48FE-8316-ACA81BB230DA|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}

https://vpc.aliyuncs.com/?Action=DeleteSslVpnServer
&RegionId=cn-hangzhou
&SslVpnServerId=vss-bp18q7hzj6largv4vk2fe
&<CommonParameters>

```

**Response example**

-   XML format

    ```
    <DeleteSslVpnServerResponse>
      <RequestId>606998F0-B94D-48FE-8316-ACA81BB230DA</RequestId>
    </DeleteSslVpnServerResponse>
    
    ```

-   JSON format

    ```
    {
    	"RequestId":"606998F0-B94D-48FE-8316-ACA81BB230DA"
    }
    ```


## Error codes {#section_mdp_gqm_vgb .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbbiden.SubUser|User not authorized to operate on the specified resource as your account is created by another user.|You are not authorized to operate on this resource. Please apply for the permission and try again.|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource. For more information, open a ticket.|
|400|VpnGateway.Configuring|The specified service is configuring.|The service is being configured. Please try again later.|
|400|VpnGateway.FinancialLocked|The specified service is financial locked.|The specified service has an overdue payment. Renew your account to settle the payment.|

[See common error codes](https://error-center.aliyun.com/status/product/Vpc)

