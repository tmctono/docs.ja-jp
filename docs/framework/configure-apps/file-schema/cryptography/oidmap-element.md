---
title: <oidMap> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: 6c57810389acbd58e6d2e05277a6f26fa0aac8c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149518"
---
# <a name="oidmap-element"></a><span data-ttu-id="59cc8-102">\<oidMap> 要素</span><span class="sxs-lookup"><span data-stu-id="59cc8-102">\<oidMap> Element</span></span>

<span data-ttu-id="59cc8-103">クラスに対する asn.1 オブジェクト識別子 (OID) マッピングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="59cc8-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**

## <a name="syntax"></a><span data-ttu-id="59cc8-104">構文</span><span class="sxs-lookup"><span data-stu-id="59cc8-104">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59cc8-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="59cc8-105">Attributes and Elements</span></span>  

 <span data-ttu-id="59cc8-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="59cc8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59cc8-107">属性</span><span class="sxs-lookup"><span data-stu-id="59cc8-107">Attributes</span></span>  

 <span data-ttu-id="59cc8-108">なし。</span><span class="sxs-lookup"><span data-stu-id="59cc8-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59cc8-109">子要素</span><span class="sxs-lookup"><span data-stu-id="59cc8-109">Child Elements</span></span>  
  
|<span data-ttu-id="59cc8-110">要素</span><span class="sxs-lookup"><span data-stu-id="59cc8-110">Element</span></span>|<span data-ttu-id="59cc8-111">説明</span><span class="sxs-lookup"><span data-stu-id="59cc8-111">Description</span></span>|  
|-------------|-----------------|  
|[\<oidEntry>](oidentry-element.md)|<span data-ttu-id="59cc8-112">Asn.1 OID をフレンドリ名にマップします。</span><span class="sxs-lookup"><span data-stu-id="59cc8-112">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59cc8-113">親要素</span><span class="sxs-lookup"><span data-stu-id="59cc8-113">Parent Elements</span></span>  
  
|<span data-ttu-id="59cc8-114">要素</span><span class="sxs-lookup"><span data-stu-id="59cc8-114">Element</span></span>|<span data-ttu-id="59cc8-115">説明</span><span class="sxs-lookup"><span data-stu-id="59cc8-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="59cc8-116">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="59cc8-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="59cc8-117">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="59cc8-117">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="59cc8-118">要素が含まれてい `cryptographySettings` ます。</span><span class="sxs-lookup"><span data-stu-id="59cc8-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="59cc8-119">例</span><span class="sxs-lookup"><span data-stu-id="59cc8-119">Example</span></span>  

 <span data-ttu-id="59cc8-120">次の例は、要素を使用して、 **\<oidMap>** RIPEMD-160 ハッシュアルゴリズムの OID とそのハッシュアルゴリズムの実装とのマッピングを格納する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="59cc8-120">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59cc8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="59cc8-121">See also</span></span>

- [<span data-ttu-id="59cc8-122">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="59cc8-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="59cc8-123">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="59cc8-123">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="59cc8-124">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="59cc8-124">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="59cc8-125">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="59cc8-125">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="59cc8-126">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="59cc8-126">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
