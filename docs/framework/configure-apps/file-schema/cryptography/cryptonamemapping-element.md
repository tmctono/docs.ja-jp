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
ms.openlocfilehash: bcf7894dba66736fcc1a30af9b5557549ef25e7d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674767"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="89f7e-102">\<cryptoNameMapping > 要素</span><span class="sxs-lookup"><span data-stu-id="89f7e-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="89f7e-103">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="89f7e-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="89f7e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="89f7e-104">\<configuration></span></span>  
<span data-ttu-id="89f7e-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="89f7e-105">\<mscorlib></span></span>  
<span data-ttu-id="89f7e-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="89f7e-106">\<cryptographySettings></span></span>  
<span data-ttu-id="89f7e-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="89f7e-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f7e-108">構文</span><span class="sxs-lookup"><span data-stu-id="89f7e-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89f7e-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="89f7e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="89f7e-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="89f7e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89f7e-111">属性</span><span class="sxs-lookup"><span data-stu-id="89f7e-111">Attributes</span></span>  
 <span data-ttu-id="89f7e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="89f7e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89f7e-113">子要素</span><span class="sxs-lookup"><span data-stu-id="89f7e-113">Child Elements</span></span>  
  
|<span data-ttu-id="89f7e-114">要素</span><span class="sxs-lookup"><span data-stu-id="89f7e-114">Element</span></span>|<span data-ttu-id="89f7e-115">説明</span><span class="sxs-lookup"><span data-stu-id="89f7e-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="89f7e-116">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="89f7e-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="89f7e-117">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="89f7e-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89f7e-118">親要素</span><span class="sxs-lookup"><span data-stu-id="89f7e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="89f7e-119">要素</span><span class="sxs-lookup"><span data-stu-id="89f7e-119">Element</span></span>|<span data-ttu-id="89f7e-120">説明</span><span class="sxs-lookup"><span data-stu-id="89f7e-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="89f7e-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="89f7e-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="89f7e-122">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="89f7e-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="89f7e-123">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="89f7e-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="89f7e-124">含まれています、 \<cryptographySettings > 要素。</span><span class="sxs-lookup"><span data-stu-id="89f7e-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="89f7e-125">例</span><span class="sxs-lookup"><span data-stu-id="89f7e-125">Example</span></span>  
 <span data-ttu-id="89f7e-126">次の例は、使用する方法を示します、  **\<cryptoNameMapping >** 暗号化クラスを参照して、ランタイムを構成する要素。</span><span class="sxs-lookup"><span data-stu-id="89f7e-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="89f7e-127">文字列"RSA"を渡すことができますし、<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドを使用して、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>を返すメソッドを`MyCryptoRSAClass`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="89f7e-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="89f7e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="89f7e-128">See also</span></span>

- [<span data-ttu-id="89f7e-129">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="89f7e-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="89f7e-130">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="89f7e-130">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="89f7e-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="89f7e-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="89f7e-132">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="89f7e-132">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
