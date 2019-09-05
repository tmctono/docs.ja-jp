---
title: <enforceFIPSPolicy> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f90abf9f6c2bc0aed2cf01558b2c0cca4e967e81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252645"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="db4b6-102">\<enforceFIPSPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="db4b6-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="db4b6-103">暗号化アルゴリズムが連邦情報処理規格 (FIPS: Federal Information Processing Standard) に準拠する必要があるコンピューターの構成要件を強制するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="db4b6-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
<span data-ttu-id="db4b6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="db4b6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="db4b6-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="db4b6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="db4b6-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<enforceFIPSPolicy>**</span><span class="sxs-lookup"><span data-stu-id="db4b6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db4b6-107">構文</span><span class="sxs-lookup"><span data-stu-id="db4b6-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db4b6-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="db4b6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="db4b6-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="db4b6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db4b6-110">属性</span><span class="sxs-lookup"><span data-stu-id="db4b6-110">Attributes</span></span>  
  
|<span data-ttu-id="db4b6-111">属性</span><span class="sxs-lookup"><span data-stu-id="db4b6-111">Attribute</span></span>|<span data-ttu-id="db4b6-112">説明</span><span class="sxs-lookup"><span data-stu-id="db4b6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db4b6-113">enabled</span><span class="sxs-lookup"><span data-stu-id="db4b6-113">enabled</span></span>|<span data-ttu-id="db4b6-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="db4b6-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="db4b6-115">暗号化アルゴリズムが FIPS に準拠している必要があるコンピューター構成要件の適用を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="db4b6-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="db4b6-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="db4b6-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="db4b6-117">値</span><span class="sxs-lookup"><span data-stu-id="db4b6-117">Value</span></span>|<span data-ttu-id="db4b6-118">説明</span><span class="sxs-lookup"><span data-stu-id="db4b6-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="db4b6-119">暗号化アルゴリズムが FIPS に準拠するようにコンピューターが構成されている場合は、その要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="db4b6-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="db4b6-120">クラスが FIPS に準拠していないアルゴリズムを実装している場合`Create` 、そのクラスのコンストラクターまたはメソッドは、そのコンピューターで実行されるときに例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="db4b6-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="db4b6-121">既定値です。</span><span class="sxs-lookup"><span data-stu-id="db4b6-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="db4b6-122">アプリケーションで使用される暗号化アルゴリズムは、コンピューターの構成に関係なく、FIPS に準拠している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db4b6-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db4b6-123">子要素</span><span class="sxs-lookup"><span data-stu-id="db4b6-123">Child Elements</span></span>  
 <span data-ttu-id="db4b6-124">なし。</span><span class="sxs-lookup"><span data-stu-id="db4b6-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db4b6-125">親要素</span><span class="sxs-lookup"><span data-stu-id="db4b6-125">Parent Elements</span></span>  
  
|<span data-ttu-id="db4b6-126">要素</span><span class="sxs-lookup"><span data-stu-id="db4b6-126">Element</span></span>|<span data-ttu-id="db4b6-127">説明</span><span class="sxs-lookup"><span data-stu-id="db4b6-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="db4b6-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="db4b6-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="db4b6-129">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db4b6-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db4b6-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="db4b6-130">Remarks</span></span>  
 <span data-ttu-id="db4b6-131">.NET Framework 2.0 以降では、暗号化アルゴリズムを実装するクラスの作成は、コンピューターの構成によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="db4b6-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="db4b6-132">アルゴリズムが FIPS に準拠していることを必要とするようにコンピューターが構成されており、クラスが FIPS に準拠していないアルゴリズムを実装している場合、そのクラスのインスタンスを作成しようとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="db4b6-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="db4b6-133">コンストラクターは<xref:System.InvalidOperationException>例外`Create`をスローし、メソッドは<xref:System.Reflection.TargetInvocationException>内部<xref:System.InvalidOperationException>例外を使用して例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="db4b6-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="db4b6-134">構成が FIPS に準拠している必要があり、アプリケーションで fips に準拠していないアルゴリズムが使用されているコンピューターでアプリケーションを実行する場合は、構成ファイルでこの要素を使用して、共通言語ランタイム (CLR) がFIPS 準拠の強制。</span><span class="sxs-lookup"><span data-stu-id="db4b6-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="db4b6-135">この要素は、.NET Framework 2.0 Service Pack 1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="db4b6-135">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db4b6-136">例</span><span class="sxs-lookup"><span data-stu-id="db4b6-136">Example</span></span>  
 <span data-ttu-id="db4b6-137">次の例は、CLR が FIPS 準拠を強制しないようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="db4b6-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db4b6-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="db4b6-138">See also</span></span>

- [<span data-ttu-id="db4b6-139">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="db4b6-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="db4b6-140">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="db4b6-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="db4b6-141">暗号モデル</span><span class="sxs-lookup"><span data-stu-id="db4b6-141">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
