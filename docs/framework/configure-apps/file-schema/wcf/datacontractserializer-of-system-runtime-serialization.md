---
title: <dataContractSerializer> <の> の。
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: a8d379e7a37bca0cdb58836a6afdf814320e2411
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190190"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a>\<dataContractSerializer> の \<system.runtime.serialization>

<xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a>構文  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a>属性および要素  

 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|要素|説明|  
|-------------|-----------------|  
|ignoreExtensionDataObject|エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。 この属性は、`<dataContractSerializer>` 要素の下の `<behavior>` でのみ設定可能です。|  
|maxItemsInObjectGraph|シリアル化または逆シリアル化する項目の最大数を指定する整数。 この属性は 65536 です。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|逆シリアル化時に <xref:System.Runtime.Serialization.DataContractSerializer> が使用する既知の型が含まれています。<br /><br /> データコントラクトと既知の型の詳細については、「 [データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。|  
  
## <a name="remarks"></a>解説  

 既知の型の詳細については、「」 <xref:System.Runtime.Serialization.DataContractSerializer> および「 [データコントラクトの既知の型](../../../wcf/feature-details/data-contract-known-types.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [既知のデータ コントラクト型](../../../wcf/feature-details/data-contract-known-types.md)
