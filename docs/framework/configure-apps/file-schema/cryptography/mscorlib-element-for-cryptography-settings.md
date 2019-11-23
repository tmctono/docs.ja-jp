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
ms.openlocfilehash: 4e2159cda5f35b5795804dede09ec17d07d71b23
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699746"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="edec5-102">暗号化設定の mscorlib > 要素を \<する</span><span class="sxs-lookup"><span data-stu-id="edec5-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="edec5-103">[\<cryptographySettings > 要素](cryptographysettings-element.md)を格納します。</span><span class="sxs-lookup"><span data-stu-id="edec5-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="edec5-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="edec5-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="edec5-105">&nbsp;&nbsp; **\<mscorlib >**</span><span class="sxs-lookup"><span data-stu-id="edec5-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edec5-106">構文</span><span class="sxs-lookup"><span data-stu-id="edec5-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edec5-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="edec5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="edec5-108">次のセクションでは、属性、子要素、親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="edec5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edec5-109">属性</span><span class="sxs-lookup"><span data-stu-id="edec5-109">Attributes</span></span>  
 <span data-ttu-id="edec5-110">[なし]。</span><span class="sxs-lookup"><span data-stu-id="edec5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="edec5-111">子要素</span><span class="sxs-lookup"><span data-stu-id="edec5-111">Child Elements</span></span>  
  
|<span data-ttu-id="edec5-112">要素</span><span class="sxs-lookup"><span data-stu-id="edec5-112">Element</span></span>|<span data-ttu-id="edec5-113">説明</span><span class="sxs-lookup"><span data-stu-id="edec5-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="edec5-114">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="edec5-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="edec5-115">親要素</span><span class="sxs-lookup"><span data-stu-id="edec5-115">Parent Elements</span></span>  
  
|<span data-ttu-id="edec5-116">要素</span><span class="sxs-lookup"><span data-stu-id="edec5-116">Element</span></span>|<span data-ttu-id="edec5-117">説明</span><span class="sxs-lookup"><span data-stu-id="edec5-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="edec5-118">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="edec5-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="edec5-119">例</span><span class="sxs-lookup"><span data-stu-id="edec5-119">Example</span></span>  
 <span data-ttu-id="edec5-120">次の例は、 **\<mscorlib >** 要素を使用して、暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="edec5-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="edec5-121">その後、文字列 "RSA" を <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> メソッドに渡し、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> メソッドを使用して `MyCryptoRSAClass` オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="edec5-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="edec5-122">参照</span><span class="sxs-lookup"><span data-stu-id="edec5-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="edec5-123">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="edec5-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="edec5-124">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="edec5-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="edec5-125">暗号サービス</span><span class="sxs-lookup"><span data-stu-id="edec5-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="edec5-126">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="edec5-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
