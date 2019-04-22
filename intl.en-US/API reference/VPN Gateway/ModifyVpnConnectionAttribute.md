# ModifyVpnConnectionAttribute {#reference_i4w_xmt_ndb .reference}

Modifies the configurations of an IPsec connection.

## Debug {#section_r1x_kfy_5gb .section}

By using [API Explorer](https://api.aliyun.com/#product=Vpc&api=DescribeVpcAttribute), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#section_cch_pjg_mdb .section}

|Parameter|Type|Required?|Example value|Description|
|:--------|:---|:--------|-------------|:----------|
|Action|String|Yes|ModifyVpnConnectionAttribute| The name of this action. Value:

 ModifyVpnConnectionAttribute

 |
|RegionId|String|Yes|cn-shanghai| The ID of the region to which the IPsec connection belongs.

 To query the region ID, call DescribeRegions.

 |
|VpnConnectionId|String|Yes|vco-bp1bbi27hojx80nck9k1i|The ID of the IPsec connection.|
|ClientToken|String|No|02fb3da4-130e-11e9-8e44-0016e04115b| A client token used to guarantee the idempotence of requests.

 This parameter value is generated by the client and must be unique. It must be 1 to 64 ASCII characters in length.

 |
|EffectImmediately|Boolean |No|false| Indicates whether to delete a successfully negotiated IPsec tunnel and initiate a negotiation again. Valid value:

-   true: Negotiate immediately after the configuration is completed.

-   false \(default\): Negotiate when traffic is detected over the network.


 |
|IkeConfig|JSON String|No|ikev1, ikev2| The configurations of phase one negotiation:

-   IkeConfig.Psk: Used for authentication between the IPsec VPN gateway and the customer gateway. By default, this parameter is generated randomly and can contain up to 100 characters. You can also manually specify the key.

-   IkeConfig.IkeVersion: The version of the IKE protocol. Valid values: ikev1 | ikev2. Default value: ikev1.

-   IkeConfig. IkeMode: The negotiation mode of IKE V1. Valid values: main \(main mode\) | aggressive \(aggressive mode\). Default value: main.

-   IkeConfig. IkeEncAlg: The encryption algorithm of phase one negotiation. Valid values: aes | aes192 | aes256 | des | 3des. Default value: aes.

-   IkeConfig.IkeAuthAlg: The authentication algorithm of phase one negotiation. Valid values: md5 | sha1. Default value: sha.

-   IkeConfig.IkePfs: The Diffie-Hellman key exchange algorithm used by phase one negotiation. Valid values: group1 | group2 | group5 | group14 | group24. Default value: group2.

-   IkeConfig.IkeLifetime: The SA lifecycle as the result of phase one negotiation. Value range of n: \[0, 86400\]. Default value: 86400. The unit is second.

-   IkeConfig.LocalIdIPsec: The identification of the VPN gateway. This parameter can contain up to 100 characters and the default value is the public IP address of the VPN gateway.

-   IkeConfig.LocalIdIPsec: The identification of the VPN gateway. This parameter can contain up to 100 characters and the default value is the public IP address of the VPN gateway.


 |
|IpsecConfig|JSON String|No|aes| The configurations of phase-two negotiation:

-   IpsecConfig.IpsecEncAlg: The encryption algorithm of phase-two negotiation. Valid value: aes | aes192 | aes256 | des | 3des. Default value: aes.

-   IpsecConfig. IpsecAuthAlg: The authentication algorithm of phase-two negotiation. Valid value: md5 | sha1. Default value: sha1.

-   IpsecConfig. IpsecPfs: Forward packets of all protocols. The Diffie-Hellman key exchange algorithm used by phase-one negotiation. Valid value: group1 | group2 | group5 | group14 | group24. Default value: group2.

-   IpsecConfig. IpsecLifetime: The SA lifecycle as the result of phase-two negotiation. The valid value is \[0, 86400\], the unit is second and the default value is 86400.


 |
|LocalSubnet|String|Yes|1.1.1.0/24,1.1.2.0/24|The CIDR block of the VPC to be connected with the on-premises data center. This parameter is used for phase two negotiation. Separate multiple CIDR blocks with commas \(,\). For example, 192.168.1.0/24,192.168.2.0/24.|
|Name|String|No|IPsec| The name of the IPsec connection.

 The name must be 2 to 128 characters in length and can contain letters, numbers, periods \(.\), underscores \(\_\), and hyphens \(-\). The name must start with a letter. It cannot start with `http://`  or `https://`.

 |
|RemoteSubnet|String|No|1.1.1.0/24,1.1.2.0/24|The CIDR block of the local data center. This parameter is used for phase-two negotiation. Separate multiple CIDR blocks with commas \(,\). For example, 92.168.3.0/24, 192.168.4.0/24.|

## Response parameters {#section_ugs_f1g_cz .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|VpnConnectionId|String|vco-bp1bbi27hojx80nck9k1i| The ID of the IPsec connection.

 |
|CustomerGatewayId|String|vpn-bp1q8bgx4xnkm2ogj0fiu| The ID of the customer gateway.

 |
|VpnGatewayId|String|vpn-bp1q8bgx4xnkm2ogj0fiu| The ID of the VPN Gateway.

 |
|Name|String|xxxxxxx| The name of the IPsec connection.

 |
|LocalSubnet|String|1.1.1.0/24,1.1.2.0/24| The CIDR block of the VPC.

 |
|RemoteSubnet|String|1.1.1.0/24,1.1.2.0/24| The CIDR block of the on-premises data center.

 |
|CreateTime|Long|1492753817000| The time at which the IPsec connection was created.

 |
|Description|String|xxxxxxx| The description.

 |
|EffectImmediately|Boolean|false| Indicates whether the IPsec connection takes effect immediately.

 |
|IkeConfig| | | Configurations of phase one negotiation.

 |
|└IkeAuthAlg|String|sha1| The IKE authentication algorithm. SHA-1 and MD5 are supported.

 |
|└IkeEncAlg|String|aes| The IKE encryption algorithm.

 |
|└IkeLifetime|Long|86400| The IKE lifetime.

 |
|└IkeMode|String|main| The IKE mode. Both main mode and aggressive mode are supported.

 The main mode features high security. If NAT traversal is enabled, we recommend that you select the aggressive mode.

 |
|└IkePfs|String|group2| The DH group. Valid values:**group1 | group2 | group5 | group14 | group24**

 |
|└IkeVersion|String|ikev1| The IKE version.

 |
|└LocalId|String|116.62.69.64| The local ID. It is the IP address of the VPN Gateway by default. Both FQDN and IP formats are supported.

 |
|└Psk|String|pgw6dy7d1i8in7x5| The pre-shared key.

 |
|└RemoteId|String|139.196.32.167| The peer ID. By default, it is the IP address of the customer gateway. Both FQDN and IP formats are supported.

 |
|IpsecConfig| | | Configurations of phase two negotiation.

 |
|└IpsecAuthAlg|String|sha1| The IPsec authentication algorithm. Both SHA-1 and MD5 are supported.

 |
|└IpsecEncAlg|String|aes| The IPsec encryption algorithm.

 |
|└IpsecLifetime|Long|86400| The IPsec lifetime.

 |
|└IpsecPfs|String|group2| The DH group.

 |
|RequestId|String|7DB79D0C-5F27-4AB5-995B-79BE55102F90| The ID of the request.

 |

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}

https://vpc.aliyuncs.com/?Action=ModifyVpnConnectionAttribute
&RegionId= cn-shanghai
&VpnConnectionId=vco-bp1bbi27hojx80nck9k1i
&<CommonParameters>

```

**Response example**

-   XML format

    ```
    <ModifyVpnConnectionAttributeResponse>
      <Name>vpn connection test</Name>
      <CustomerGatewayId>cgw-bp1pvpl9r9adju6l5nxck</CustomerGatewayId>
      <RemoteSubnet>2.2.2.0/24</RemoteSubnet>
      <IpsecConfig>
        <IpsecLifetime>86400</IpsecLifetime>
        <IpsecAuthAlg>sha1</IpsecAuthAlg>
        <IpsecPfs>group2</IpsecPfs>
        <IpsecEncAlg>aes</IpsecEncAlg>
      </IpsecConfig>
      <EffectImmediately>false</EffectImmediately>
      <VpnGatewayId>vpn-bp1q8bgx4xnkm2ogj0fiu</VpnGatewayId>
      <CreateTime>1492753817000</CreateTime>
      <VpnConnectionId>vco-bp10lz7aejumd2vxoqgev</VpnConnectionId>
      <RequestId>57070A3D-38F2-40A6-A1C9-DB14542EF54D</RequestId>
      <LocalSubnet>1.1.1.0/24,1.1.2.0/24</LocalSubnet>
      <IkeConfig>
        <IkeEncAlg>aes</IkeEncAlg>
        <RemoteId>139.196.32.167</RemoteId>
        <IkePfs>group2</IkePfs>
        <IkeAuthAlg>sha1</IkeAuthAlg>
        <Psk>pgw6dy7d1i8in7x5</Psk>
        <IkeMode>main</IkeMode>
        <IkeLifetime>86400</IkeLifetime>
        <IkeVersion>ikev1</IkeVersion>
        <LocalId>116.62.69.64</LocalId>
      </IkeConfig>
    </ModifyVpnConnectionAttributeResponse>
    
    ```

-   JSON format

    ```
    {
    	"CustomerGatewayId":"cgw-bp1pvpl9r9adju6l5nxck",
    	"Name":"vpn connection test",
    	"RemoteSubnet":"2.2.2.0/24",
    	"IpsecConfig":{
    		"IpsecLifetime":86400,
    		"IpsecAuthAlg":"sha1",
    		"IpsecPfs":"group2",
    		"IpsecEncAlg":"aes"
    	},
    	"VpnGatewayId":"vpn-bp1q8bgx4xnkm2ogj0fiu",
    	"EffectImmediately":false,
    	"RequestId":"7DB79D0C-5F27-4AB5-995B-79BE55102F90",
    	"VpnConnectionId":"vco-bp10lz7aejumd2vxoqgev",
    	"CreateTime":1492753817000,
    	"LocalSubnet":"1.1.1.0/24,1.1.2.0/24",
    	"IkeConfig":{
    		"IkeEncAlg":"aes",
    		"IkePfs":"group2",
    		"RemoteId":"139.196.32.167",
    		"IkeAuthAlg":"sha1",
    		"Psk":"pgw6dy7d1i8in7x5",
    		"IkeMode":"main",
    		"IkeLifetime":86400,
    		"IkeVersion":"ikev1",
    		"LocalId":"116.62.69.64"
    	}
    }
    ```


## Error codes {#section_g3p_tt2_chb .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbbiden.SubUser|User not authorized to operate on the specified resource as your account is created by another user.|You are not authorized to operate on this resource.|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|
|404|InvalidVpnConnectionInstanceId.NotFound|The specified vpn connection instance id does not exist.|The specified VPN connection does not exist.|
|400|VpnGateway.Configuring|The specified service is configuring.|The specified service is been configured.|
|400|VpnGateway.FinancialLocked|The specified service is financial locked.|The specified service is financial locked.|
|400|InvalidName|The name is not valid|The name format is invalid.|

[See common error codes](https://error-center.aliyun.com/status/product/Vpc)
