---
title: <cryptoClass> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: db3681ea141bb7e3905f6a470f5c74ce05f6ef4b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699795"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="c7454-102">@no__t 0cryptoClass > 要素</span><span class="sxs-lookup"><span data-stu-id="c7454-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="c7454-103">[\<nameEntry>](nameentry-element.md) 要素内の表示名へのマッピングを持つ暗号化クラスを含みます。</span><span class="sxs-lookup"><span data-stu-id="c7454-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="c7454-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c7454-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c7454-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c7454-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="c7454-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7454-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="c7454-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<cryptoNameMapping >** を行います。](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7454-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="c7454-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0cryptoClasses (10) >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7454-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>  
<span data-ttu-id="c7454-109">&nbsp; @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t-7 @ no__t-8 @-9 **&nbsp;1cryptoClass >** を @ にします。</span><span class="sxs-lookup"><span data-stu-id="c7454-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7454-110">構文</span><span class="sxs-lookup"><span data-stu-id="c7454-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7454-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c7454-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c7454-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7454-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7454-113">属性</span><span class="sxs-lookup"><span data-stu-id="c7454-113">Attributes</span></span>  
  
|<span data-ttu-id="c7454-114">属性</span><span class="sxs-lookup"><span data-stu-id="c7454-114">Attribute</span></span>|<span data-ttu-id="c7454-115">説明</span><span class="sxs-lookup"><span data-stu-id="c7454-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="c7454-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c7454-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c7454-117">暗号化クラスの情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="c7454-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="c7454-118">この属性を使用して、クラスの短い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7454-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="c7454-119">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7454-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7454-120">子要素</span><span class="sxs-lookup"><span data-stu-id="c7454-120">Child Elements</span></span>  
 <span data-ttu-id="c7454-121">なし。</span><span class="sxs-lookup"><span data-stu-id="c7454-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7454-122">親要素</span><span class="sxs-lookup"><span data-stu-id="c7454-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c7454-123">要素</span><span class="sxs-lookup"><span data-stu-id="c7454-123">Element</span></span>|<span data-ttu-id="c7454-124">説明</span><span class="sxs-lookup"><span data-stu-id="c7454-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c7454-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c7454-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="c7454-126">[\<nameEntry>](nameentry-element.md) 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="c7454-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="c7454-127">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="c7454-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="c7454-128">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="c7454-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="c7454-129">[ \<cryptographySettings >](cryptographysettings-element.md)要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="c7454-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c7454-130">例</span><span class="sxs-lookup"><span data-stu-id="c7454-130">Example</span></span>  
 <span data-ttu-id="c7454-131">次の例は、 **\<cryptoClass >** 要素を使用して、暗号化クラスを参照し、ランタイムを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c7454-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="c7454-132">その後、文字列 "RSA" を <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> メソッドに渡し、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> メソッドを使用して `MyCryptoRSAClass` オブジェクトを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="c7454-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c7454-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7454-133">See also</span></span>

- [<span data-ttu-id="c7454-134">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="c7454-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c7454-135">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c7454-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c7454-136">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="c7454-136">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="c7454-137">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="c7454-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
