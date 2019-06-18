# DeleteSslVpnClientCert {#reference_i4w_xmt_ndb .reference}

Deletes an SSL-VPN client certificate.

## Debug {#section_n13_pfy_5gb .section}

By using [API Explorer](https://api.aliyun.com/#product=Vpc&api=DescribeVpcAttribute), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#section_cch_pjg_mdb .section}

|Parameter|Type|Required?|Example value|Description|
|:--------|:---|:--------|-------------|:----------|
|Action|String|Yes|DeleteSslVpnClientCert| The name of this action. Value:

 DeleteSslVpnClientCert

 |
|RegionId|String|Yes|cn-hangzhou| The region to which the SSL-VPN client certificate belongs.

 To query the region ID, call DescribeRegions.

 |
|SslVpnClientCertId|String|Yes|vsc-bp1n8wcf134yl0osrcg98| The ID of the SSL-VPN client certificate.

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

https://vpc.aliyuncs.com/?Action=DeleteSslVpnClientCert
&RegionId=cn-hangzhou
&SslVpnClientCertId=vsc-bp1n8wcf134yl0osrcg98
&<CommonRequestParameters>

```

 **Response example** 

-   XML format

    ```
    <DeleteSslVpnClientCertResponse>
      <RequestId>606998F0-B94D-48FE-8316-ACA81BB230DA</RequestId>
    </DeleteSslVpnClientCertResponse>
    
    ```

-   JSON format

    ```
    {
    	"RequestId":"606998F0-B94D-48FE-8316-ACA81BB230DA"
    }
    ```


## Error codes {#section_ezy_rzn_vgb .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbbiden.SubUser|User not authorized to operate on the specified resource as your account is created by another user.|You are not authorized to operate on this resource. Please apply for the permission and try again.|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource. For more information, open a ticket.|
|400|VpnGateway.Configuring|The specified service is configuring.|The service is being configured. Please try again later.|

[See common error codes](https://error-center.aliyun.com/status/product/Vpc)
