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
ms.openlocfilehash: 89b96edcf1da20698cd203e78fa27e644fa69cc3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201825"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="74886-102">\<cryptoClasses> 要素</span><span class="sxs-lookup"><span data-stu-id="74886-102">\<cryptoClasses> Element</span></span>

<span data-ttu-id="74886-103">要素内の表示名へのマッピングを持つ暗号化クラスの一覧が含まれてい [\<nameEntry>](nameentry-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="74886-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**  
  
## <a name="syntax"></a><span data-ttu-id="74886-104">構文</span><span class="sxs-lookup"><span data-stu-id="74886-104">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74886-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="74886-105">Attributes and Elements</span></span>  

 <span data-ttu-id="74886-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="74886-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74886-107">属性</span><span class="sxs-lookup"><span data-stu-id="74886-107">Attributes</span></span>  

 <span data-ttu-id="74886-108">なし。</span><span class="sxs-lookup"><span data-stu-id="74886-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="74886-109">子要素</span><span class="sxs-lookup"><span data-stu-id="74886-109">Child Elements</span></span>  
  
|<span data-ttu-id="74886-110">要素</span><span class="sxs-lookup"><span data-stu-id="74886-110">Element</span></span>|<span data-ttu-id="74886-111">説明</span><span class="sxs-lookup"><span data-stu-id="74886-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoClass>](cryptoclass-element.md)|<span data-ttu-id="74886-112">要素内のフレンドリ名へのマッピングを持つ暗号化クラスを格納 **\<nameEntry>** します。</span><span class="sxs-lookup"><span data-stu-id="74886-112">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74886-113">親要素</span><span class="sxs-lookup"><span data-stu-id="74886-113">Parent Elements</span></span>  
  
|<span data-ttu-id="74886-114">要素</span><span class="sxs-lookup"><span data-stu-id="74886-114">Element</span></span>|<span data-ttu-id="74886-115">説明</span><span class="sxs-lookup"><span data-stu-id="74886-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="74886-116">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="74886-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="74886-117">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="74886-117">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="74886-118">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="74886-118">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="74886-119">要素が含まれてい `cryptographySettings` ます。</span><span class="sxs-lookup"><span data-stu-id="74886-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="74886-120">例</span><span class="sxs-lookup"><span data-stu-id="74886-120">Example</span></span>  

 <span data-ttu-id="74886-121">次の例は、要素を使用して暗号化クラスを参照し、ランタイムを構成する方法を示して **\<cryptoClass>** います。</span><span class="sxs-lookup"><span data-stu-id="74886-121">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="74886-122">その後、文字列 "RSA" をメソッドに渡し <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 、メソッドを使用して <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> オブジェクトを返すことができ `MyCryptoRSAClass` ます。</span><span class="sxs-lookup"><span data-stu-id="74886-122">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74886-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="74886-123">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="74886-124">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="74886-124">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="74886-125">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="74886-125">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="74886-126">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="74886-126">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="74886-127">CryptoConfig. CreateFromName のようになります。</span><span class="sxs-lookup"><span data-stu-id="74886-127">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="74886-128">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="74886-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
