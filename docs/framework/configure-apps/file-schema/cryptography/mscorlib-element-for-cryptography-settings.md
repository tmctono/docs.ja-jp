---
title: 暗号設定の <mscorlib> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: 312db8ea5ae4b66fd00faad1b788eac0356aeaa7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659597"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="bb588-102">\<暗号化設定の mscorlib > 要素</span><span class="sxs-lookup"><span data-stu-id="bb588-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="bb588-103">[ \<Cryptographysettings > 要素](cryptographysettings-element.md)を格納します。</span><span class="sxs-lookup"><span data-stu-id="bb588-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="bb588-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb588-104">\<configuration></span></span>  
<span data-ttu-id="bb588-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="bb588-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb588-106">構文</span><span class="sxs-lookup"><span data-stu-id="bb588-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb588-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bb588-107">Attributes and Elements</span></span>  
 <span data-ttu-id="bb588-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb588-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb588-109">属性</span><span class="sxs-lookup"><span data-stu-id="bb588-109">Attributes</span></span>  
 <span data-ttu-id="bb588-110">なし。</span><span class="sxs-lookup"><span data-stu-id="bb588-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb588-111">子要素</span><span class="sxs-lookup"><span data-stu-id="bb588-111">Child Elements</span></span>  
  
|<span data-ttu-id="bb588-112">要素</span><span class="sxs-lookup"><span data-stu-id="bb588-112">Element</span></span>|<span data-ttu-id="bb588-113">説明</span><span class="sxs-lookup"><span data-stu-id="bb588-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="bb588-114">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="bb588-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb588-115">親要素</span><span class="sxs-lookup"><span data-stu-id="bb588-115">Parent Elements</span></span>  
  
|<span data-ttu-id="bb588-116">要素</span><span class="sxs-lookup"><span data-stu-id="bb588-116">Element</span></span>|<span data-ttu-id="bb588-117">説明</span><span class="sxs-lookup"><span data-stu-id="bb588-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb588-118">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="bb588-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bb588-119">例</span><span class="sxs-lookup"><span data-stu-id="bb588-119">Example</span></span>  
 <span data-ttu-id="bb588-120">次の例は、  **\<mscorlib >** 要素を使用して、暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bb588-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="bb588-121">その後、文字列 "RSA" を<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドに渡し、 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>メソッドを使用してオブジェクトを`MyCryptoRSAClass`返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bb588-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bb588-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb588-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="bb588-123">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="bb588-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bb588-124">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="bb588-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bb588-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="bb588-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="bb588-126">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="bb588-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
