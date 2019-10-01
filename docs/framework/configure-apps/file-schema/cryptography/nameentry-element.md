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
ms.openlocfilehash: a339638587f8b544bbc1b0073553f6232ce09694
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699780"
---
# <a name="nameentry-element"></a><span data-ttu-id="5d42a-102">\<nameEntry > 要素</span><span class="sxs-lookup"><span data-stu-id="5d42a-102">\<nameEntry> Element</span></span>
<span data-ttu-id="5d42a-103">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="5d42a-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[<span data-ttu-id="5d42a-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="5d42a-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="5d42a-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5d42a-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="5d42a-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d42a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="5d42a-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<cryptoNameMapping >** を行います。](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d42a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="5d42a-108">&nbsp; @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t-6 @-7 **\<nameEntry > を入力**します。</span><span class="sxs-lookup"><span data-stu-id="5d42a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d42a-109">構文</span><span class="sxs-lookup"><span data-stu-id="5d42a-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d42a-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5d42a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5d42a-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d42a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d42a-112">属性</span><span class="sxs-lookup"><span data-stu-id="5d42a-112">Attributes</span></span>  
  
|<span data-ttu-id="5d42a-113">属性</span><span class="sxs-lookup"><span data-stu-id="5d42a-113">Attribute</span></span>|<span data-ttu-id="5d42a-114">説明</span><span class="sxs-lookup"><span data-stu-id="5d42a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d42a-115">**name**</span><span class="sxs-lookup"><span data-stu-id="5d42a-115">**name**</span></span>|<span data-ttu-id="5d42a-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="5d42a-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="5d42a-117">暗号化クラスが実装するアルゴリズムのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d42a-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="5d42a-118">**class**</span><span class="sxs-lookup"><span data-stu-id="5d42a-118">**class**</span></span>|<span data-ttu-id="5d42a-119">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="5d42a-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="5d42a-120">[@No__t-2cryptoClass >](cryptoclass-element.md)要素の**name**属性の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d42a-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d42a-121">子要素</span><span class="sxs-lookup"><span data-stu-id="5d42a-121">Child Elements</span></span>  
 <span data-ttu-id="5d42a-122">なし。</span><span class="sxs-lookup"><span data-stu-id="5d42a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d42a-123">親要素</span><span class="sxs-lookup"><span data-stu-id="5d42a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5d42a-124">要素</span><span class="sxs-lookup"><span data-stu-id="5d42a-124">Element</span></span>|<span data-ttu-id="5d42a-125">説明</span><span class="sxs-lookup"><span data-stu-id="5d42a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5d42a-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5d42a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="5d42a-127">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d42a-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d42a-128">コメント</span><span class="sxs-lookup"><span data-stu-id="5d42a-128">Remarks</span></span>  
 <span data-ttu-id="5d42a-129">**Name**属性には、<xref:System.Security.Cryptography> 名前空間で見つかった抽象クラスの1つの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5d42a-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="5d42a-130">抽象暗号化クラスで**Create**メソッドを呼び出すと、抽象クラス名が <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5d42a-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="5d42a-131">**CreateFromName**は、 **class**属性で示される型のインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="5d42a-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="5d42a-132">**Name**属性が RSA などの短い名前である場合は、 **CreateFromName**メソッドを呼び出すときにその名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d42a-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d42a-133">例</span><span class="sxs-lookup"><span data-stu-id="5d42a-133">Example</span></span>  
 <span data-ttu-id="5d42a-134">次の例は、 **\<nameEntry >** 要素を使用して、暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5d42a-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="5d42a-135">その後、文字列 "RSA" を <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> メソッドに渡し、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> メソッドを使用して `MyCryptoRSAClass` オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d42a-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d42a-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d42a-136">See also</span></span>

- [<span data-ttu-id="5d42a-137">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="5d42a-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5d42a-138">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="5d42a-138">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5d42a-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="5d42a-139">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="5d42a-140">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="5d42a-140">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
