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
ms.openlocfilehash: c13dd2f00e08539d2ba502058c74aa4a1525e3ff
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816111"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="8272b-102">\<enforceFIPSPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="8272b-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="8272b-103">暗号化アルゴリズムが連邦情報処理規格 (FIPS: Federal Information Processing Standard) に準拠する必要があるコンピューターの構成要件を強制するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8272b-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="8272b-104">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="8272b-104">\<configuration> Element</span></span>  
<span data-ttu-id="8272b-105">\<runtime> 要素</span><span class="sxs-lookup"><span data-stu-id="8272b-105">\<runtime> Element</span></span>  
<span data-ttu-id="8272b-106">\<enforceFIPSPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="8272b-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8272b-107">構文</span><span class="sxs-lookup"><span data-stu-id="8272b-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8272b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8272b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8272b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8272b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8272b-110">属性</span><span class="sxs-lookup"><span data-stu-id="8272b-110">Attributes</span></span>  
  
|<span data-ttu-id="8272b-111">属性</span><span class="sxs-lookup"><span data-stu-id="8272b-111">Attribute</span></span>|<span data-ttu-id="8272b-112">説明</span><span class="sxs-lookup"><span data-stu-id="8272b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8272b-113">enabled</span><span class="sxs-lookup"><span data-stu-id="8272b-113">enabled</span></span>|<span data-ttu-id="8272b-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="8272b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="8272b-115">暗号化アルゴリズムは FIPS 準拠でなければならないこと、コンピューターの構成要件の強制を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8272b-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8272b-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="8272b-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="8272b-117">値</span><span class="sxs-lookup"><span data-stu-id="8272b-117">Value</span></span>|<span data-ttu-id="8272b-118">説明</span><span class="sxs-lookup"><span data-stu-id="8272b-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="8272b-119">FIPS に準拠する暗号アルゴリズムを要求するように、コンピューターを構成する場合は、その要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8272b-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="8272b-120">クラスは、コンス トラクターは、FIPS 準拠アルゴリズムを実装している場合または`Create`そのコンピューターで実行された場合、そのクラスのメソッドが例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="8272b-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="8272b-121">既定値です。</span><span class="sxs-lookup"><span data-stu-id="8272b-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="8272b-122">アプリケーションで使用される暗号化アルゴリズムは、コンピューターの構成に関係なく、FIPS に準拠する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8272b-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8272b-123">子要素</span><span class="sxs-lookup"><span data-stu-id="8272b-123">Child Elements</span></span>  
 <span data-ttu-id="8272b-124">なし。</span><span class="sxs-lookup"><span data-stu-id="8272b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8272b-125">親要素</span><span class="sxs-lookup"><span data-stu-id="8272b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8272b-126">要素</span><span class="sxs-lookup"><span data-stu-id="8272b-126">Element</span></span>|<span data-ttu-id="8272b-127">説明</span><span class="sxs-lookup"><span data-stu-id="8272b-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8272b-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="8272b-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8272b-129">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8272b-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8272b-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="8272b-130">Remarks</span></span>  
 <span data-ttu-id="8272b-131">以降、.NET Framework 2.0 では、暗号アルゴリズムを実装するクラスの作成は、コンピューターの構成によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="8272b-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="8272b-132">FIPS に準拠するアルゴリズムを要求するように、コンピューターが構成されているクラスは、FIPS 準拠アルゴリズムを実装する場合は、そのクラスのインスタンスを作成しようとするとは、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="8272b-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="8272b-133">コンス トラクターがスロー、<xref:System.InvalidOperationException>例外、および`Create`メソッドでスロー、<xref:System.Reflection.TargetInvocationException>と内部例外<xref:System.InvalidOperationException>例外。</span><span class="sxs-lookup"><span data-stu-id="8272b-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="8272b-134">構成は、fips コンプライアンスを必要とするコンピューターでアプリケーションを実行し、アプリケーションでは fips 準拠アルゴリズムを使用することができます要素を使用してこの構成ファイルから共通言語ランタイム (CLR) を防ぐためにFIPS 準拠を適用します。</span><span class="sxs-lookup"><span data-stu-id="8272b-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="8272b-135">この要素は、.NET Framework 2.0 Service Pack 1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8272b-135">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8272b-136">例</span><span class="sxs-lookup"><span data-stu-id="8272b-136">Example</span></span>  
 <span data-ttu-id="8272b-137">次の例では、CLR が FIPS 準拠を適用することを防止する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8272b-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8272b-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="8272b-138">See also</span></span>

- [<span data-ttu-id="8272b-139">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="8272b-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="8272b-140">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="8272b-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="8272b-141">暗号モデル</span><span class="sxs-lookup"><span data-stu-id="8272b-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)
