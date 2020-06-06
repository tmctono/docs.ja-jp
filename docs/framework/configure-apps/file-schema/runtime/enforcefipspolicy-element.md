---
title: <enforceFIPSPolicy> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
ms.openlocfilehash: 0d6dd291a24928487a040c0427f058dee80bf836
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117386"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="b4f4b-102">\<enforceFIPSPolicy> 要素</span><span class="sxs-lookup"><span data-stu-id="b4f4b-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="b4f4b-103">暗号化アルゴリズムが連邦情報処理規格 (FIPS: Federal Information Processing Standard) に準拠する必要があるコンピューターの構成要件を強制するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="b4f4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="b4f4b-104">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4f4b-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b4f4b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b4f4b-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4f4b-107">属性</span><span class="sxs-lookup"><span data-stu-id="b4f4b-107">Attributes</span></span>  
  
|<span data-ttu-id="b4f4b-108">属性</span><span class="sxs-lookup"><span data-stu-id="b4f4b-108">Attribute</span></span>|<span data-ttu-id="b4f4b-109">説明</span><span class="sxs-lookup"><span data-stu-id="b4f4b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4f4b-110">enabled</span><span class="sxs-lookup"><span data-stu-id="b4f4b-110">enabled</span></span>|<span data-ttu-id="b4f4b-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="b4f4b-112">暗号化アルゴリズムが FIPS に準拠している必要があるコンピューター構成要件の適用を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-112">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b4f4b-113">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="b4f4b-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="b4f4b-114">値</span><span class="sxs-lookup"><span data-stu-id="b4f4b-114">Value</span></span>|<span data-ttu-id="b4f4b-115">Description</span><span class="sxs-lookup"><span data-stu-id="b4f4b-115">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="b4f4b-116">暗号化アルゴリズムが FIPS に準拠するようにコンピューターが構成されている場合は、その要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-116">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="b4f4b-117">クラスが FIPS に準拠していないアルゴリズムを実装している場合、そのクラスのコンストラクターまたはメソッドは、その `Create` コンピューターで実行されるときに例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-117">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="b4f4b-118">既定値です。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="b4f4b-119">アプリケーションで使用される暗号化アルゴリズムは、コンピューターの構成に関係なく、FIPS に準拠している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-119">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4f4b-120">子要素</span><span class="sxs-lookup"><span data-stu-id="b4f4b-120">Child Elements</span></span>  
 <span data-ttu-id="b4f4b-121">なし。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4f4b-122">親要素</span><span class="sxs-lookup"><span data-stu-id="b4f4b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b4f4b-123">要素</span><span class="sxs-lookup"><span data-stu-id="b4f4b-123">Element</span></span>|<span data-ttu-id="b4f4b-124">Description</span><span class="sxs-lookup"><span data-stu-id="b4f4b-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b4f4b-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b4f4b-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4f4b-127">解説</span><span class="sxs-lookup"><span data-stu-id="b4f4b-127">Remarks</span></span>  
 <span data-ttu-id="b4f4b-128">.NET Framework 2.0 以降では、暗号化アルゴリズムを実装するクラスの作成は、コンピューターの構成によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-128">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="b4f4b-129">アルゴリズムが FIPS に準拠していることを必要とするようにコンピューターが構成されており、クラスが FIPS に準拠していないアルゴリズムを実装している場合、そのクラスのインスタンスを作成しようとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-129">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="b4f4b-130">コンストラクターは <xref:System.InvalidOperationException> 例外をスローし、 `Create` メソッドは <xref:System.Reflection.TargetInvocationException> 内部例外を使用して例外をスローし <xref:System.InvalidOperationException> ます。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-130">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="b4f4b-131">構成が FIPS に準拠しているコンピューターでアプリケーションを実行していて、アプリケーションが fips に準拠していないアルゴリズムを使用している場合は、構成ファイルでこの要素を使用して、共通言語ランタイム (CLR) が FIPS 準拠を強制しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-131">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="b4f4b-132">この要素は、.NET Framework 2.0 Service Pack 1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-132">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4f4b-133">例</span><span class="sxs-lookup"><span data-stu-id="b4f4b-133">Example</span></span>  
 <span data-ttu-id="b4f4b-134">次の例は、CLR が FIPS 準拠を強制しないようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b4f4b-134">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4f4b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4f4b-135">See also</span></span>

- [<span data-ttu-id="b4f4b-136">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b4f4b-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b4f4b-137">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b4f4b-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b4f4b-138">暗号モデル</span><span class="sxs-lookup"><span data-stu-id="b4f4b-138">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
