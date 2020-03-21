---
title: <cryptoNameMapping> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: d31c5cd52ffe0e2a6eb5784735e76436d216444b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155220"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="743c8-102">\<>要素の暗号化名マッピング</span><span class="sxs-lookup"><span data-stu-id="743c8-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="743c8-103">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="743c8-103">Contains mappings of classes to friendly names.</span></span>  

<span data-ttu-id="743c8-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="743c8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="743c8-105">&nbsp;&nbsp;[**\<>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="743c8-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="743c8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<暗号化設定>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="743c8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="743c8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>名マッピング**</span><span class="sxs-lookup"><span data-stu-id="743c8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>

## <a name="syntax"></a><span data-ttu-id="743c8-108">構文</span><span class="sxs-lookup"><span data-stu-id="743c8-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="743c8-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="743c8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="743c8-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="743c8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="743c8-111">属性</span><span class="sxs-lookup"><span data-stu-id="743c8-111">Attributes</span></span>  
 <span data-ttu-id="743c8-112">[なし] :</span><span class="sxs-lookup"><span data-stu-id="743c8-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="743c8-113">子要素</span><span class="sxs-lookup"><span data-stu-id="743c8-113">Child Elements</span></span>  
  
|<span data-ttu-id="743c8-114">要素</span><span class="sxs-lookup"><span data-stu-id="743c8-114">Element</span></span>|<span data-ttu-id="743c8-115">説明</span><span class="sxs-lookup"><span data-stu-id="743c8-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="743c8-116">nameEntry 要素のフレンドリ名にマッピングされている暗号化クラスの一覧>含まれています。 \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="743c8-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="743c8-117">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="743c8-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="743c8-118">親要素</span><span class="sxs-lookup"><span data-stu-id="743c8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="743c8-119">要素</span><span class="sxs-lookup"><span data-stu-id="743c8-119">Element</span></span>|<span data-ttu-id="743c8-120">説明</span><span class="sxs-lookup"><span data-stu-id="743c8-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="743c8-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="743c8-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="743c8-122">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="743c8-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="743c8-123">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="743c8-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="743c8-124">\<cryptographySettings >要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="743c8-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="743c8-125">例</span><span class="sxs-lookup"><span data-stu-id="743c8-125">Example</span></span>  
 <span data-ttu-id="743c8-126">次の例は**\<、cryptoNameMapping>** 要素を使用して、暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="743c8-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="743c8-127">その後、<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドに文字列 "RSA" を渡し、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>メソッドを使用して`MyCryptoRSAClass`オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="743c8-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="743c8-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="743c8-128">See also</span></span>

- [<span data-ttu-id="743c8-129">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="743c8-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="743c8-130">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="743c8-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="743c8-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="743c8-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="743c8-132">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="743c8-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
