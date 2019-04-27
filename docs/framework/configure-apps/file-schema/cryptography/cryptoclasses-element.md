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
ms.openlocfilehash: 7a03729f075645a230c660ff4c6469e0f5f3a51e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674780"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="6cc89-102">\<cryptoClasses > 要素</span><span class="sxs-lookup"><span data-stu-id="6cc89-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="6cc89-103">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="6cc89-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="6cc89-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6cc89-104">\<configuration></span></span>  
<span data-ttu-id="6cc89-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="6cc89-105">\<mscorlib></span></span>  
<span data-ttu-id="6cc89-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="6cc89-106">\<cryptographySettings></span></span>  
<span data-ttu-id="6cc89-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="6cc89-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="6cc89-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="6cc89-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cc89-109">構文</span><span class="sxs-lookup"><span data-stu-id="6cc89-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6cc89-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6cc89-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6cc89-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6cc89-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6cc89-112">属性</span><span class="sxs-lookup"><span data-stu-id="6cc89-112">Attributes</span></span>  
 <span data-ttu-id="6cc89-113">なし。</span><span class="sxs-lookup"><span data-stu-id="6cc89-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6cc89-114">子要素</span><span class="sxs-lookup"><span data-stu-id="6cc89-114">Child Elements</span></span>  
  
|<span data-ttu-id="6cc89-115">要素</span><span class="sxs-lookup"><span data-stu-id="6cc89-115">Element</span></span>|<span data-ttu-id="6cc89-116">説明</span><span class="sxs-lookup"><span data-stu-id="6cc89-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6cc89-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="6cc89-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="6cc89-118">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスを含みます。</span><span class="sxs-lookup"><span data-stu-id="6cc89-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6cc89-119">親要素</span><span class="sxs-lookup"><span data-stu-id="6cc89-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6cc89-120">要素</span><span class="sxs-lookup"><span data-stu-id="6cc89-120">Element</span></span>|<span data-ttu-id="6cc89-121">説明</span><span class="sxs-lookup"><span data-stu-id="6cc89-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6cc89-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="6cc89-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="6cc89-123">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="6cc89-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="6cc89-124">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="6cc89-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="6cc89-125">`cryptographySettings`要素を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="6cc89-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6cc89-126">例</span><span class="sxs-lookup"><span data-stu-id="6cc89-126">Example</span></span>  
 <span data-ttu-id="6cc89-127">次の例では、  **\<cryptoClass >** 暗号化クラスを参照して、ランタイムを構成する要素。</span><span class="sxs-lookup"><span data-stu-id="6cc89-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="6cc89-128">文字列"RSA"を渡すことができますし、<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドを使用して、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>を返すメソッドを`MyCryptoRSAClass`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6cc89-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6cc89-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cc89-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="6cc89-130">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="6cc89-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="6cc89-131">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6cc89-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="6cc89-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="6cc89-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="6cc89-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="6cc89-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="6cc89-134">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="6cc89-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
