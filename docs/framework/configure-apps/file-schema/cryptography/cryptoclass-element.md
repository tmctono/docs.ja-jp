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
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088656"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="873d8-102">\<cryptoClass> 要素</span><span class="sxs-lookup"><span data-stu-id="873d8-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="873d8-103">要素内のフレンドリ名へのマッピングを持つ暗号化クラスを格納 [\<nameEntry>](nameentry-element.md) します。</span><span class="sxs-lookup"><span data-stu-id="873d8-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a><span data-ttu-id="873d8-104">構文</span><span class="sxs-lookup"><span data-stu-id="873d8-104">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="873d8-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="873d8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="873d8-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="873d8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="873d8-107">属性</span><span class="sxs-lookup"><span data-stu-id="873d8-107">Attributes</span></span>  
  
|<span data-ttu-id="873d8-108">属性</span><span class="sxs-lookup"><span data-stu-id="873d8-108">Attribute</span></span>|<span data-ttu-id="873d8-109">説明</span><span class="sxs-lookup"><span data-stu-id="873d8-109">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="873d8-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="873d8-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="873d8-111">暗号化クラスの情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="873d8-111">Contains the information for the cryptography class.</span></span> <span data-ttu-id="873d8-112">この属性を使用して、クラスの短い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="873d8-112">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="873d8-113">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="873d8-113">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="873d8-114">子要素</span><span class="sxs-lookup"><span data-stu-id="873d8-114">Child Elements</span></span>  
 <span data-ttu-id="873d8-115">なし。</span><span class="sxs-lookup"><span data-stu-id="873d8-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="873d8-116">親要素</span><span class="sxs-lookup"><span data-stu-id="873d8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="873d8-117">要素</span><span class="sxs-lookup"><span data-stu-id="873d8-117">Element</span></span>|<span data-ttu-id="873d8-118">Description</span><span class="sxs-lookup"><span data-stu-id="873d8-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="873d8-119">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="873d8-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="873d8-120">要素内の表示名へのマッピングを持つ暗号化クラスの一覧が含まれてい [\<nameEntry>](nameentry-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="873d8-120">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="873d8-121">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="873d8-121">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="873d8-122">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="873d8-122">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="873d8-123">要素が含まれてい [\<cryptographySettings>](cryptographysettings-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="873d8-123">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="873d8-124">例</span><span class="sxs-lookup"><span data-stu-id="873d8-124">Example</span></span>  
 <span data-ttu-id="873d8-125">次の例は、要素を使用して暗号化クラスを参照し、ランタイムを構成する方法を示して **\<cryptoClass>** います。</span><span class="sxs-lookup"><span data-stu-id="873d8-125">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="873d8-126">その後、文字列 "RSA" をメソッドに渡し <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 、メソッドを使用して <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> オブジェクトを返すことができ `MyCryptoRSAClass` ます。</span><span class="sxs-lookup"><span data-stu-id="873d8-126">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="873d8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="873d8-127">See also</span></span>

- [<span data-ttu-id="873d8-128">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="873d8-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="873d8-129">暗号設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="873d8-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="873d8-130">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="873d8-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="873d8-131">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="873d8-131">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
