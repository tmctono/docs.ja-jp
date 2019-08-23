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
ms.openlocfilehash: d8f4d4aa9c80990cdf858da9fcdf6465438866cf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927569"
---
# <a name="nameentry-element"></a><span data-ttu-id="c95f5-102">\<nameEntry > 要素</span><span class="sxs-lookup"><span data-stu-id="c95f5-102">\<nameEntry> Element</span></span>
<span data-ttu-id="c95f5-103">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="c95f5-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="c95f5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c95f5-104">\<configuration></span></span>  
<span data-ttu-id="c95f5-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="c95f5-105">\<mscorlib></span></span>  
<span data-ttu-id="c95f5-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="c95f5-106">\<cryptographySettings></span></span>  
<span data-ttu-id="c95f5-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="c95f5-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="c95f5-108">\<nameEntry ></span><span class="sxs-lookup"><span data-stu-id="c95f5-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c95f5-109">構文</span><span class="sxs-lookup"><span data-stu-id="c95f5-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c95f5-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c95f5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c95f5-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c95f5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c95f5-112">属性</span><span class="sxs-lookup"><span data-stu-id="c95f5-112">Attributes</span></span>  
  
|<span data-ttu-id="c95f5-113">属性</span><span class="sxs-lookup"><span data-stu-id="c95f5-113">Attribute</span></span>|<span data-ttu-id="c95f5-114">説明</span><span class="sxs-lookup"><span data-stu-id="c95f5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c95f5-115">**name**</span><span class="sxs-lookup"><span data-stu-id="c95f5-115">**name**</span></span>|<span data-ttu-id="c95f5-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c95f5-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c95f5-117">暗号化クラスが実装するアルゴリズムのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c95f5-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="c95f5-118">**class**</span><span class="sxs-lookup"><span data-stu-id="c95f5-118">**class**</span></span>|<span data-ttu-id="c95f5-119">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c95f5-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="c95f5-120">Cryptoclass > 要素の**name**属性[の値を指定します。 \<](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="c95f5-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c95f5-121">子要素</span><span class="sxs-lookup"><span data-stu-id="c95f5-121">Child Elements</span></span>  
 <span data-ttu-id="c95f5-122">なし。</span><span class="sxs-lookup"><span data-stu-id="c95f5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c95f5-123">親要素</span><span class="sxs-lookup"><span data-stu-id="c95f5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c95f5-124">要素</span><span class="sxs-lookup"><span data-stu-id="c95f5-124">Element</span></span>|<span data-ttu-id="c95f5-125">説明</span><span class="sxs-lookup"><span data-stu-id="c95f5-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c95f5-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c95f5-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="c95f5-127">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="c95f5-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c95f5-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="c95f5-128">Remarks</span></span>  
 <span data-ttu-id="c95f5-129">**Name**属性には、名前<xref:System.Security.Cryptography>空間で見つかった抽象クラスの1つの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c95f5-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="c95f5-130">抽象暗号化クラスで**Create**メソッドを呼び出すと、抽象クラス名が<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="c95f5-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="c95f5-131">**CreateFromName**は、 **class**属性で示される型のインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="c95f5-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="c95f5-132">**Name**属性が RSA などの短い名前である場合は、 **CreateFromName**メソッドを呼び出すときにその名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c95f5-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c95f5-133">例</span><span class="sxs-lookup"><span data-stu-id="c95f5-133">Example</span></span>  
 <span data-ttu-id="c95f5-134">次の例は、  **\<nameentry >** 要素を使用して、暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c95f5-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="c95f5-135">その後、文字列 "RSA" を<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドに渡し、 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>メソッドを使用してオブジェクトを`MyCryptoRSAClass`返すことができます。</span><span class="sxs-lookup"><span data-stu-id="c95f5-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c95f5-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="c95f5-136">See also</span></span>

- [<span data-ttu-id="c95f5-137">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="c95f5-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c95f5-138">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c95f5-138">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c95f5-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="c95f5-139">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="c95f5-140">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="c95f5-140">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
