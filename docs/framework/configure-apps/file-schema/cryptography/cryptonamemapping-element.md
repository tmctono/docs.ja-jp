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
ms.openlocfilehash: c2652ac73c1d55f09a1f8511603003dc6d7291f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659644"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="9334b-102">\<cryptoNameMapping > 要素</span><span class="sxs-lookup"><span data-stu-id="9334b-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="9334b-103">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="9334b-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="9334b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9334b-104">\<configuration></span></span>  
<span data-ttu-id="9334b-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="9334b-105">\<mscorlib></span></span>  
<span data-ttu-id="9334b-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="9334b-106">\<cryptographySettings></span></span>  
<span data-ttu-id="9334b-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="9334b-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9334b-108">構文</span><span class="sxs-lookup"><span data-stu-id="9334b-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9334b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9334b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9334b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9334b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9334b-111">属性</span><span class="sxs-lookup"><span data-stu-id="9334b-111">Attributes</span></span>  
 <span data-ttu-id="9334b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="9334b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9334b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="9334b-113">Child Elements</span></span>  
  
|<span data-ttu-id="9334b-114">要素</span><span class="sxs-lookup"><span data-stu-id="9334b-114">Element</span></span>|<span data-ttu-id="9334b-115">説明</span><span class="sxs-lookup"><span data-stu-id="9334b-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="9334b-116">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="9334b-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="9334b-117">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="9334b-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9334b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="9334b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9334b-119">要素</span><span class="sxs-lookup"><span data-stu-id="9334b-119">Element</span></span>|<span data-ttu-id="9334b-120">説明</span><span class="sxs-lookup"><span data-stu-id="9334b-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9334b-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9334b-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="9334b-122">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="9334b-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="9334b-123">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="9334b-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="9334b-124">Cryptographysettings > 要素を\<格納します。</span><span class="sxs-lookup"><span data-stu-id="9334b-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9334b-125">例</span><span class="sxs-lookup"><span data-stu-id="9334b-125">Example</span></span>  
 <span data-ttu-id="9334b-126">次の例は、  **\<cryptoNameMapping >** 要素を使用して、暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9334b-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="9334b-127">その後、文字列 "RSA" を<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドに渡し、 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>メソッドを使用してオブジェクトを`MyCryptoRSAClass`返すことができます。</span><span class="sxs-lookup"><span data-stu-id="9334b-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9334b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="9334b-128">See also</span></span>

- [<span data-ttu-id="9334b-129">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="9334b-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9334b-130">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9334b-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9334b-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="9334b-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="9334b-132">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="9334b-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
