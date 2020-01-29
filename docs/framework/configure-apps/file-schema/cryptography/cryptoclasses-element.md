---
title: <cryptoClasses> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 6601417f0b80f623b7698c4b072c35eca44343b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732880"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="b9da7-102">\<cryptoClasses > 要素</span><span class="sxs-lookup"><span data-stu-id="b9da7-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="b9da7-103">[\<nameEntry>](nameentry-element.md) 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="b9da7-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="b9da7-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b9da7-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b9da7-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b9da7-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="b9da7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9da7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="b9da7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[ **cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9da7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="b9da7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**cryptoClasses >**</span><span class="sxs-lookup"><span data-stu-id="b9da7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9da7-109">構文</span><span class="sxs-lookup"><span data-stu-id="b9da7-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9da7-110">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b9da7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b9da7-111">次のセクションでは、属性、子要素、親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9da7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9da7-112">属性</span><span class="sxs-lookup"><span data-stu-id="b9da7-112">Attributes</span></span>  
 <span data-ttu-id="b9da7-113">ありません。</span><span class="sxs-lookup"><span data-stu-id="b9da7-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b9da7-114">子要素</span><span class="sxs-lookup"><span data-stu-id="b9da7-114">Child Elements</span></span>  
  
|<span data-ttu-id="b9da7-115">要素</span><span class="sxs-lookup"><span data-stu-id="b9da7-115">Element</span></span>|<span data-ttu-id="b9da7-116">説明</span><span class="sxs-lookup"><span data-stu-id="b9da7-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9da7-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="b9da7-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="b9da7-118">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスを含みます。</span><span class="sxs-lookup"><span data-stu-id="b9da7-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b9da7-119">親要素</span><span class="sxs-lookup"><span data-stu-id="b9da7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b9da7-120">要素</span><span class="sxs-lookup"><span data-stu-id="b9da7-120">Element</span></span>|<span data-ttu-id="b9da7-121">説明</span><span class="sxs-lookup"><span data-stu-id="b9da7-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b9da7-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b9da7-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="b9da7-123">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="b9da7-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="b9da7-124">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="b9da7-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="b9da7-125">`cryptographySettings`要素を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="b9da7-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b9da7-126">使用例</span><span class="sxs-lookup"><span data-stu-id="b9da7-126">Example</span></span>  
 <span data-ttu-id="b9da7-127">次の例は、\<の**cryptoclass >** 要素を使用して、暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b9da7-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="b9da7-128">その後、文字列 "RSA" を <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> メソッドに渡し、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> メソッドを使用して `MyCryptoRSAClass` オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="b9da7-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9da7-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9da7-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="b9da7-130">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b9da7-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b9da7-131">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b9da7-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b9da7-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="b9da7-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="b9da7-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="b9da7-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="b9da7-134">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="b9da7-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
