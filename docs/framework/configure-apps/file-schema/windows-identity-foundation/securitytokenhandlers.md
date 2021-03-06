---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: d892fbd802ed366ca7af9b85fbf5c23d4d27e0f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157006"
---
# \<securityTokenHandlers>

エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**  
  
## <a name="syntax"></a>構文  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  

 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|name|トークンハンドラーコレクションの名前を指定します。 フレームワークによって認識される値は、"ActAs" と "OnBehalfOf" だけです。 これらのいずれかの名前でトークンハンドラーコレクションが指定されている場合、ActAs または OnBehalfOf トークンをそれぞれ処理するときにコレクションが使用されます。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<add>](add.md)|トークンハンドラーコレクションにセキュリティトークンハンドラーを追加します。|  
|[\<clear>](clear.md)|すべてのセキュリティトークンハンドラーをトークンハンドラーコレクションから削除します。|  
|[\<remove>](remove.md)|トークンハンドラーコレクションからセキュリティトークンハンドラーを削除します。|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|トークンハンドラーのコレクションの構成を提供します。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|サービスレベルの id 設定を指定します。|  
  
## <a name="remarks"></a>解説  

 サービス構成では、セキュリティトークンハンドラーの1つ以上の名前付きコレクションを指定できます。 属性を使用して、コレクションの名前を指定でき `name` ます。 フレームワークによって処理される名前は、"ActAs" と "OnBehalfOf" だけです。 これらのコレクションにハンドラーが存在する場合は、トークンの処理時に既定のハンドラーではなく、Security Token Service (STS) によって使用され `ActAs` `OnBehalfOf` ます。  
  
 既定では、コレクションには、、、、、、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler> <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 、および <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> の各ハンドラー型が設定されます。 コレクションは、、、およびの各要素を使用して変更でき `<add>` `<remove>` `<clear>` ます。 コレクション内に存在する特定の種類のハンドラーが1つだけであることを確認する必要があります。 たとえば、クラスからハンドラーを派生させる場合、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ハンドラーまたはが <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 1 つのコレクションで構成されていることがありますが、両方を構成することはできません。  
  
 `<securityTokenHandlerConfiguration>`コレクション内のハンドラーの構成設定を指定するには、要素を使用します。 この要素によって指定された設定は、サービスで指定された設定よりも要素を介してオーバーライドされ [\<identityConfiguration>](identityconfiguration.md) ます。 いくつかの組み込みハンドラー型を含む一部のハンドラーは、要素の子要素を通じて追加の構成をサポートでき `<add>` ます。 ハンドラーに指定された設定は、コレクションまたはサービスで指定された同等の設定よりも優先されます。
