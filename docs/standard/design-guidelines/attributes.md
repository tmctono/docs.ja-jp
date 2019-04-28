---
title: 属性
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: KrzysztofCwalina
ms.openlocfilehash: 6d4cc6615b7f7346e9c8fc2a7264025f318c8a3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785568"
---
# <a name="attributes"></a><span data-ttu-id="681b0-102">属性</span><span class="sxs-lookup"><span data-stu-id="681b0-102">Attributes</span></span>
<span data-ttu-id="681b0-103"><xref:System.Attribute?displayProperty=nameWithType> カスタム属性を定義するために使用する基本クラス。</span><span class="sxs-lookup"><span data-stu-id="681b0-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="681b0-104">属性は、アセンブリ、型、メンバー、およびパラメーターなどのプログラミング要素に追加できる注釈です。</span><span class="sxs-lookup"><span data-stu-id="681b0-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="681b0-105">アセンブリのメタデータに格納されていて、リフレクション Api を使用して実行時にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="681b0-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="681b0-106">たとえば、フレームワークを定義、 <xref:System.ObsoleteAttribute>、型またはメンバーは推奨されていることを示す、型またはメンバーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="681b0-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="681b0-107">属性には、1 つ以上のプロパティ、属性に関連する追加のデータを受け渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="681b0-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="681b0-108">たとえば、`ObsoleteAttribute`のリリースに関する追加情報を実行することが、型またはメンバーが非推奨とし、廃止された API を置き換える新しい Api の説明。</span><span class="sxs-lookup"><span data-stu-id="681b0-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="681b0-109">属性が適用されるときに、属性の一部のプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="681b0-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="681b0-110">これらと呼びます必要なプロパティまたは必須の引数を位置指定コンス トラクターのパラメーターとして表されるためです。</span><span class="sxs-lookup"><span data-stu-id="681b0-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="681b0-111">たとえば、<xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A>のプロパティ、<xref:System.Diagnostics.ConditionalAttribute>は必要なプロパティです。</span><span class="sxs-lookup"><span data-stu-id="681b0-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="681b0-112">属性を適用した場合に指定する必ずしもプロパティは省略可能なプロパティ (または省略可能な引数) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="681b0-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="681b0-113">設定可能なプロパティで表されます。</span><span class="sxs-lookup"><span data-stu-id="681b0-113">They are represented by settable properties.</span></span> <span data-ttu-id="681b0-114">コンパイラは、属性が適用されるときに、これらのプロパティを設定する特別な構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="681b0-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="681b0-115">たとえば、<xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>プロパティは省略可能な引数を表します。</span><span class="sxs-lookup"><span data-stu-id="681b0-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="681b0-116">**✓ DO** 「属性」サフィックスを持つカスタム属性クラスの名前</span><span class="sxs-lookup"><span data-stu-id="681b0-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="681b0-117">**✓ DO** 適用、<xref:System.AttributeUsageAttribute>カスタム属性にします。</span><span class="sxs-lookup"><span data-stu-id="681b0-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="681b0-118">**✓ DO** 省略可能な引数の設定可能なプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="681b0-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="681b0-119">**✓ DO** 必須の引数の取得専用のプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="681b0-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="681b0-120">**✓ DO** 必須の引数に対応するプロパティを初期化するコンス トラクターのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="681b0-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="681b0-121">各パラメーターは、対応するプロパティとして (大文字小文字が異なる) には、同じ名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="681b0-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="681b0-122">**X AVOID** 省略可能な引数に対応するプロパティを初期化するコンス トラクターのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="681b0-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="681b0-123">つまり、コンス トラクターと setter の両方で設定できるプロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="681b0-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="681b0-124">このガイドラインでは非常に明示的などの引数は省略可能ですし、これは必須であり、2 つの方法で同じことを行う必要はなくなります。</span><span class="sxs-lookup"><span data-stu-id="681b0-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="681b0-125">**X AVOID** カスタム属性のコンス トラクターのオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="681b0-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="681b0-126">コンス トラクターの 1 つだけのことを明確に伝達をユーザーにどの引数が必要ですし、これは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="681b0-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="681b0-127">**✓ DO** 可能であれば、カスタム属性クラスをシールします。</span><span class="sxs-lookup"><span data-stu-id="681b0-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="681b0-128">これにより、属性の参照、高速化。</span><span class="sxs-lookup"><span data-stu-id="681b0-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="681b0-129">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="681b0-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="681b0-130">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="681b0-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="681b0-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="681b0-131">See also</span></span>

- [<span data-ttu-id="681b0-132">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="681b0-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="681b0-133">使用方法のガイドライン</span><span class="sxs-lookup"><span data-stu-id="681b0-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
