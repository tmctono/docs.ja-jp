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
ms.openlocfilehash: d1d805f7154c18dba2dcd4eb7228cc200d8da811
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155182"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="49f73-102">暗号設定の \<mscorlib> 要素</span><span class="sxs-lookup"><span data-stu-id="49f73-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="49f73-103">[ \<cryptographySettings> 要素](cryptographysettings-element.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="49f73-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<mscorlib>**  
  
## <a name="syntax"></a><span data-ttu-id="49f73-104">構文</span><span class="sxs-lookup"><span data-stu-id="49f73-104">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49f73-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="49f73-105">Attributes and Elements</span></span>  
 <span data-ttu-id="49f73-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="49f73-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49f73-107">属性</span><span class="sxs-lookup"><span data-stu-id="49f73-107">Attributes</span></span>  
 <span data-ttu-id="49f73-108">なし。</span><span class="sxs-lookup"><span data-stu-id="49f73-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="49f73-109">子要素</span><span class="sxs-lookup"><span data-stu-id="49f73-109">Child Elements</span></span>  
  
|<span data-ttu-id="49f73-110">要素</span><span class="sxs-lookup"><span data-stu-id="49f73-110">Element</span></span>|<span data-ttu-id="49f73-111">説明</span><span class="sxs-lookup"><span data-stu-id="49f73-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="49f73-112">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="49f73-112">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49f73-113">親要素</span><span class="sxs-lookup"><span data-stu-id="49f73-113">Parent Elements</span></span>  
  
|<span data-ttu-id="49f73-114">要素</span><span class="sxs-lookup"><span data-stu-id="49f73-114">Element</span></span>|<span data-ttu-id="49f73-115">説明</span><span class="sxs-lookup"><span data-stu-id="49f73-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="49f73-116">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="49f73-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="49f73-117">例</span><span class="sxs-lookup"><span data-stu-id="49f73-117">Example</span></span>  
 <span data-ttu-id="49f73-118">次の例は、要素を使用して **\<mscorlib>** 暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="49f73-118">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="49f73-119">その後、文字列 "RSA" をメソッドに渡し <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 、メソッドを使用して <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> オブジェクトを返すことができ `MyCryptoRSAClass` ます。</span><span class="sxs-lookup"><span data-stu-id="49f73-119">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="49f73-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="49f73-120">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="49f73-121">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="49f73-121">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="49f73-122">暗号設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="49f73-122">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="49f73-123">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="49f73-123">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="49f73-124">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="49f73-124">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
