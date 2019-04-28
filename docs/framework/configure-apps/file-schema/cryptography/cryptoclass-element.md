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
ms.openlocfilehash: da78140806ab8dbe7b7cb5e321e82755774ff25d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705260"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="201c2-102">\<cryptoClass > 要素</span><span class="sxs-lookup"><span data-stu-id="201c2-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="201c2-103">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 要素内の表示名へのマッピングを持つ暗号化クラスを含みます。</span><span class="sxs-lookup"><span data-stu-id="201c2-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="201c2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="201c2-104">\<configuration></span></span>  
<span data-ttu-id="201c2-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="201c2-105">\<mscorlib></span></span>  
<span data-ttu-id="201c2-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="201c2-106">\<cryptographySettings></span></span>  
<span data-ttu-id="201c2-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="201c2-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="201c2-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="201c2-108">\<cryptoClasses></span></span>  
<span data-ttu-id="201c2-109">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="201c2-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="201c2-110">構文</span><span class="sxs-lookup"><span data-stu-id="201c2-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="201c2-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="201c2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="201c2-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="201c2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="201c2-113">属性</span><span class="sxs-lookup"><span data-stu-id="201c2-113">Attributes</span></span>  
  
|<span data-ttu-id="201c2-114">属性</span><span class="sxs-lookup"><span data-stu-id="201c2-114">Attribute</span></span>|<span data-ttu-id="201c2-115">説明</span><span class="sxs-lookup"><span data-stu-id="201c2-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="201c2-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="201c2-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="201c2-117">暗号化クラスの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="201c2-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="201c2-118">この属性を使用して、クラスの短い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="201c2-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="201c2-119">指定された条件に一致する文字列を指定する必要があります[完全修飾型名の指定](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)します。</span><span class="sxs-lookup"><span data-stu-id="201c2-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="201c2-120">子要素</span><span class="sxs-lookup"><span data-stu-id="201c2-120">Child Elements</span></span>  
 <span data-ttu-id="201c2-121">なし。</span><span class="sxs-lookup"><span data-stu-id="201c2-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="201c2-122">親要素</span><span class="sxs-lookup"><span data-stu-id="201c2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="201c2-123">要素</span><span class="sxs-lookup"><span data-stu-id="201c2-123">Element</span></span>|<span data-ttu-id="201c2-124">説明</span><span class="sxs-lookup"><span data-stu-id="201c2-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="201c2-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="201c2-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="201c2-126">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="201c2-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="201c2-127">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="201c2-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="201c2-128">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="201c2-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="201c2-129">[ \<cryptographySettings >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="201c2-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="201c2-130">例</span><span class="sxs-lookup"><span data-stu-id="201c2-130">Example</span></span>  
 <span data-ttu-id="201c2-131">次の例では、  **\<cryptoClass >** 暗号化クラスを参照して、ランタイムを構成する要素。</span><span class="sxs-lookup"><span data-stu-id="201c2-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="201c2-132">文字列"RSA"を渡すことができますし、<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドを使用して、<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>を返すメソッドを`MyCryptoRSAClass`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="201c2-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="201c2-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="201c2-133">See also</span></span>

- [<span data-ttu-id="201c2-134">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="201c2-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="201c2-135">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="201c2-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="201c2-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="201c2-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="201c2-137">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="201c2-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
