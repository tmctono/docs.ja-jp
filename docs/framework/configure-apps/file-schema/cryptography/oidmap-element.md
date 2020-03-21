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
ms.openlocfilehash: a28eaf68fe1e6ab3f26592eee5ae2d0f2e7a3256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155168"
---
# <a name="oidmap-element"></a><span data-ttu-id="a287b-102">\<oidMap>要素</span><span class="sxs-lookup"><span data-stu-id="a287b-102">\<oidMap> Element</span></span>
<span data-ttu-id="a287b-103">ASN.1 オブジェクト識別子 (OID) のクラスへのマッピングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a287b-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

<span data-ttu-id="a287b-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a287b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a287b-105">&nbsp;&nbsp;[**\<>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a287b-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="a287b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<暗号化設定>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="a287b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="a287b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="a287b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a287b-108">構文</span><span class="sxs-lookup"><span data-stu-id="a287b-108">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a287b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a287b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a287b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a287b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a287b-111">属性</span><span class="sxs-lookup"><span data-stu-id="a287b-111">Attributes</span></span>  
 <span data-ttu-id="a287b-112">[なし] :</span><span class="sxs-lookup"><span data-stu-id="a287b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a287b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="a287b-113">Child Elements</span></span>  
  
|<span data-ttu-id="a287b-114">要素</span><span class="sxs-lookup"><span data-stu-id="a287b-114">Element</span></span>|<span data-ttu-id="a287b-115">説明</span><span class="sxs-lookup"><span data-stu-id="a287b-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a287b-116">\<oidエントリー></span><span class="sxs-lookup"><span data-stu-id="a287b-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="a287b-117">ASN.1 OID をフレンドリ名にマップします。</span><span class="sxs-lookup"><span data-stu-id="a287b-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a287b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="a287b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a287b-119">要素</span><span class="sxs-lookup"><span data-stu-id="a287b-119">Element</span></span>|<span data-ttu-id="a287b-120">説明</span><span class="sxs-lookup"><span data-stu-id="a287b-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a287b-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a287b-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="a287b-122">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="a287b-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="a287b-123">要素を`cryptographySettings`格納します。</span><span class="sxs-lookup"><span data-stu-id="a287b-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a287b-124">例</span><span class="sxs-lookup"><span data-stu-id="a287b-124">Example</span></span>  
 <span data-ttu-id="a287b-125">次の例では**\<、oidMap>** 要素を使用して、そのハッシュ アルゴリズムの実装に対する RIPEMD-160 ハッシュ アルゴリズムの OID のマッピングを格納する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a287b-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a287b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a287b-126">See also</span></span>

- [<span data-ttu-id="a287b-127">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="a287b-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a287b-128">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a287b-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a287b-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="a287b-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="a287b-130">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="a287b-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="a287b-131">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="a287b-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
