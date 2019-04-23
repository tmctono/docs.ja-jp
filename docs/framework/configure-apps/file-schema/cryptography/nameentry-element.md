---
title: <nameEntry> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: 97521ba9073820beeea62f5fc7cab480b5422fb0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225327"
---
# <a name="nameentry-element"></a><span data-ttu-id="8d496-102">\<nameEntry > 要素</span><span class="sxs-lookup"><span data-stu-id="8d496-102">\<nameEntry> Element</span></span>
<span data-ttu-id="8d496-103">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="8d496-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="8d496-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8d496-104">\<configuration></span></span>  
<span data-ttu-id="8d496-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="8d496-105">\<mscorlib></span></span>  
<span data-ttu-id="8d496-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="8d496-106">\<cryptographySettings></span></span>  
<span data-ttu-id="8d496-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="8d496-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="8d496-108">\<nameEntry></span><span class="sxs-lookup"><span data-stu-id="8d496-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d496-109">構文</span><span class="sxs-lookup"><span data-stu-id="8d496-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d496-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8d496-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8d496-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d496-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d496-112">属性</span><span class="sxs-lookup"><span data-stu-id="8d496-112">Attributes</span></span>  
  
|<span data-ttu-id="8d496-113">属性</span><span class="sxs-lookup"><span data-stu-id="8d496-113">Attribute</span></span>|<span data-ttu-id="8d496-114">説明</span><span class="sxs-lookup"><span data-stu-id="8d496-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d496-115">**name**</span><span class="sxs-lookup"><span data-stu-id="8d496-115">**name**</span></span>|<span data-ttu-id="8d496-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="8d496-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="8d496-117">暗号化クラスを実装するアルゴリズムのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d496-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="8d496-118">**class**</span><span class="sxs-lookup"><span data-stu-id="8d496-118">**class**</span></span>|<span data-ttu-id="8d496-119">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="8d496-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="8d496-120">値を指定します、**名前**属性、 [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)要素。</span><span class="sxs-lookup"><span data-stu-id="8d496-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d496-121">子要素</span><span class="sxs-lookup"><span data-stu-id="8d496-121">Child Elements</span></span>  
 <span data-ttu-id="8d496-122">なし。</span><span class="sxs-lookup"><span data-stu-id="8d496-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d496-123">親要素</span><span class="sxs-lookup"><span data-stu-id="8d496-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8d496-124">要素</span><span class="sxs-lookup"><span data-stu-id="8d496-124">Element</span></span>|<span data-ttu-id="8d496-125">説明</span><span class="sxs-lookup"><span data-stu-id="8d496-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8d496-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="8d496-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="8d496-127">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d496-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d496-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d496-128">Remarks</span></span>  
 <span data-ttu-id="8d496-129">**名前**属性は、抽象クラスのいずれかの名前を指定できます、<xref:System.Security.Cryptography>名前空間。</span><span class="sxs-lookup"><span data-stu-id="8d496-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="8d496-130">呼び出すと、**作成**抽象暗号化クラスのメソッドは、抽象クラスの名前に渡される、<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="8d496-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="8d496-131">**CreateFromName**で示される型のインスタンスを返します、**クラス**属性。</span><span class="sxs-lookup"><span data-stu-id="8d496-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="8d496-132">場合、**名前**属性は、短い名前では、RSA などを呼び出すときに、その名前を使用できます、 **CreateFromName**メソッド。</span><span class="sxs-lookup"><span data-stu-id="8d496-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d496-133">例</span><span class="sxs-lookup"><span data-stu-id="8d496-133">Example</span></span>  
 <span data-ttu-id="8d496-134">次の例は、使用する方法を示します、  **\<nameEntry >** 暗号化クラスを参照して、ランタイムを構成する要素。</span><span class="sxs-lookup"><span data-stu-id="8d496-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="8d496-135">文字列"RSA"を渡すことができますし、<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドを使用して、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>を返すメソッドを`MyCryptoRSAClass`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8d496-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8d496-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d496-136">See also</span></span>

- [<span data-ttu-id="8d496-137">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="8d496-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="8d496-138">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="8d496-138">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="8d496-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="8d496-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="8d496-140">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="8d496-140">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
