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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155220"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="27e5d-102">\<cryptoNameMapping> 要素</span><span class="sxs-lookup"><span data-stu-id="27e5d-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="27e5d-103">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="27e5d-103">Contains mappings of classes to friendly names.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**

## <a name="syntax"></a><span data-ttu-id="27e5d-104">構文</span><span class="sxs-lookup"><span data-stu-id="27e5d-104">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27e5d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="27e5d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="27e5d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="27e5d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27e5d-107">属性</span><span class="sxs-lookup"><span data-stu-id="27e5d-107">Attributes</span></span>  
 <span data-ttu-id="27e5d-108">なし。</span><span class="sxs-lookup"><span data-stu-id="27e5d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="27e5d-109">子要素</span><span class="sxs-lookup"><span data-stu-id="27e5d-109">Child Elements</span></span>  
  
|<span data-ttu-id="27e5d-110">要素</span><span class="sxs-lookup"><span data-stu-id="27e5d-110">Element</span></span>|<span data-ttu-id="27e5d-111">説明</span><span class="sxs-lookup"><span data-stu-id="27e5d-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="27e5d-112">要素内の表示名へのマッピングを持つ暗号化クラスの一覧が含まれてい **\<nameEntry>** ます。</span><span class="sxs-lookup"><span data-stu-id="27e5d-112">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="27e5d-113">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="27e5d-113">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27e5d-114">親要素</span><span class="sxs-lookup"><span data-stu-id="27e5d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="27e5d-115">要素</span><span class="sxs-lookup"><span data-stu-id="27e5d-115">Element</span></span>|<span data-ttu-id="27e5d-116">説明</span><span class="sxs-lookup"><span data-stu-id="27e5d-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="27e5d-117">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="27e5d-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="27e5d-118">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="27e5d-118">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="27e5d-119">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="27e5d-119">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="27e5d-120">要素が含まれてい \<cryptographySettings> ます。</span><span class="sxs-lookup"><span data-stu-id="27e5d-120">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27e5d-121">例</span><span class="sxs-lookup"><span data-stu-id="27e5d-121">Example</span></span>  
 <span data-ttu-id="27e5d-122">次の例は、要素を使用して **\<cryptoNameMapping>** 暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="27e5d-122">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="27e5d-123">その後、文字列 "RSA" をメソッドに渡し <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 、メソッドを使用して <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> オブジェクトを返すことができ `MyCryptoRSAClass` ます。</span><span class="sxs-lookup"><span data-stu-id="27e5d-123">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27e5d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="27e5d-124">See also</span></span>

- [<span data-ttu-id="27e5d-125">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="27e5d-125">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="27e5d-126">暗号設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="27e5d-126">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="27e5d-127">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="27e5d-127">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="27e5d-128">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="27e5d-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
