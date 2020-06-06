---
title: <cryptographySettings> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: fe6de09213c6f980e8eb205a318aae50033b2a84
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155233"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="2ae7c-102">\<cryptographySettings> 要素</span><span class="sxs-lookup"><span data-stu-id="2ae7c-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="2ae7c-103">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="2ae7c-103">Contains cryptography settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**

## <a name="syntax"></a><span data-ttu-id="2ae7c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ae7c-104">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ae7c-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2ae7c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2ae7c-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ae7c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ae7c-107">属性</span><span class="sxs-lookup"><span data-stu-id="2ae7c-107">Attributes</span></span>  
 <span data-ttu-id="2ae7c-108">なし。</span><span class="sxs-lookup"><span data-stu-id="2ae7c-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2ae7c-109">子要素</span><span class="sxs-lookup"><span data-stu-id="2ae7c-109">Child Elements</span></span>  
  
|<span data-ttu-id="2ae7c-110">要素</span><span class="sxs-lookup"><span data-stu-id="2ae7c-110">Element</span></span>|<span data-ttu-id="2ae7c-111">説明</span><span class="sxs-lookup"><span data-stu-id="2ae7c-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoNameMapping>](cryptonamemapping-element.md)|<span data-ttu-id="2ae7c-112">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="2ae7c-112">Contains mappings of classes to friendly names.</span></span>|  
|[\<oidMap>](oidmap-element.md)|<span data-ttu-id="2ae7c-113">クラスに対する asn.1 オブジェクト識別子 (OID) マッピングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ae7c-113">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ae7c-114">親要素</span><span class="sxs-lookup"><span data-stu-id="2ae7c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="2ae7c-115">要素</span><span class="sxs-lookup"><span data-stu-id="2ae7c-115">Element</span></span>|<span data-ttu-id="2ae7c-116">説明</span><span class="sxs-lookup"><span data-stu-id="2ae7c-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2ae7c-117">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2ae7c-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="2ae7c-118">要素が含まれてい `cryptographySettings` ます。</span><span class="sxs-lookup"><span data-stu-id="2ae7c-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2ae7c-119">例</span><span class="sxs-lookup"><span data-stu-id="2ae7c-119">Example</span></span>  
 <span data-ttu-id="2ae7c-120">次の例では、要素を使用して、 **\<cryptographySettings>** 暗号化名マッピングと OID マッピングを格納する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2ae7c-120">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="2ae7c-121">この例では、がオブジェクトを返すようにランタイムを構成 <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> `MyHashClass` し、クラスを `MyCryptoClass` オブジェクト識別子1.3.36.2.1 にマップします。</span><span class="sxs-lookup"><span data-stu-id="2ae7c-121">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ae7c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ae7c-122">See also</span></span>

- [<span data-ttu-id="2ae7c-123">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="2ae7c-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2ae7c-124">暗号設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2ae7c-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2ae7c-125">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="2ae7c-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
