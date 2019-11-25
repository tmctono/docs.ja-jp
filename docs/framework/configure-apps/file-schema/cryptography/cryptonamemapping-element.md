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
ms.openlocfilehash: 4b3495d17e07ca611a384bf958ee06e928eb2506
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088013"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="a213c-102">\<cryptoNameMapping > 要素</span><span class="sxs-lookup"><span data-stu-id="a213c-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="a213c-103">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="a213c-103">Contains mappings of classes to friendly names.</span></span>  

<span data-ttu-id="a213c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a213c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a213c-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a213c-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="a213c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings**](cryptographysettings-element.md) ></span><span class="sxs-lookup"><span data-stu-id="a213c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="a213c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**cryptoNameMapping >**</span><span class="sxs-lookup"><span data-stu-id="a213c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a213c-108">構文</span><span class="sxs-lookup"><span data-stu-id="a213c-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a213c-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a213c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a213c-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a213c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a213c-111">属性</span><span class="sxs-lookup"><span data-stu-id="a213c-111">Attributes</span></span>  
 <span data-ttu-id="a213c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="a213c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a213c-113">子要素</span><span class="sxs-lookup"><span data-stu-id="a213c-113">Child Elements</span></span>  
  
|<span data-ttu-id="a213c-114">要素</span><span class="sxs-lookup"><span data-stu-id="a213c-114">Element</span></span>|<span data-ttu-id="a213c-115">説明</span><span class="sxs-lookup"><span data-stu-id="a213c-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="a213c-116">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="a213c-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="a213c-117">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="a213c-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a213c-118">親要素</span><span class="sxs-lookup"><span data-stu-id="a213c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a213c-119">要素</span><span class="sxs-lookup"><span data-stu-id="a213c-119">Element</span></span>|<span data-ttu-id="a213c-120">説明</span><span class="sxs-lookup"><span data-stu-id="a213c-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a213c-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a213c-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="a213c-122">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="a213c-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="a213c-123">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="a213c-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="a213c-124">\<cryptographySettings > 要素を格納します。</span><span class="sxs-lookup"><span data-stu-id="a213c-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a213c-125">例</span><span class="sxs-lookup"><span data-stu-id="a213c-125">Example</span></span>  
 <span data-ttu-id="a213c-126">次の例は、 **\<cryptoNameMapping >** 要素を使用して、暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a213c-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="a213c-127">その後、文字列 "RSA" を <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> メソッドに渡し、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> メソッドを使用して `MyCryptoRSAClass` オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="a213c-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a213c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a213c-128">See also</span></span>

- [<span data-ttu-id="a213c-129">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="a213c-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a213c-130">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a213c-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a213c-131">暗号サービス</span><span class="sxs-lookup"><span data-stu-id="a213c-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="a213c-132">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="a213c-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
