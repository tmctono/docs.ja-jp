---
title: 属性
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: c7bbbda88bd2fddb235b9ae639848e08a452c913
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741785"
---
# <a name="attributes"></a><span data-ttu-id="2e518-102">属性</span><span class="sxs-lookup"><span data-stu-id="2e518-102">Attributes</span></span>
<span data-ttu-id="2e518-103"><xref:System.Attribute?displayProperty=nameWithType> は、カスタム属性を定義するために使用される基本クラスです。</span><span class="sxs-lookup"><span data-stu-id="2e518-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>

 <span data-ttu-id="2e518-104">属性は、アセンブリ、型、メンバー、パラメーターなどのプログラミング要素に追加できる注釈です。</span><span class="sxs-lookup"><span data-stu-id="2e518-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="2e518-105">これらは、アセンブリのメタデータに格納され、リフレクション Api を使用して実行時にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2e518-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="2e518-106">たとえば、フレームワークは <xref:System.ObsoleteAttribute>を定義します。これを型またはメンバーに適用して、型またはメンバーが非推奨とされたことを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="2e518-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>

 <span data-ttu-id="2e518-107">属性には、属性に関連する追加データを格納する1つ以上のプロパティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2e518-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="2e518-108">たとえば、`ObsoleteAttribute` は、型またはメンバーが非推奨とされたリリースに関する追加情報を伝達し、新しい Api の説明で古い API を置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="2e518-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>

 <span data-ttu-id="2e518-109">属性を適用するときは、属性の一部のプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e518-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="2e518-110">これらは、位置指定コンストラクターパラメーターとして表現されるため、必須プロパティまたは必須の引数と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2e518-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="2e518-111">たとえば、<xref:System.Diagnostics.ConditionalAttribute> の <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> プロパティは必須プロパティです。</span><span class="sxs-lookup"><span data-stu-id="2e518-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>

 <span data-ttu-id="2e518-112">属性が適用されるときに必ずしも指定する必要がないプロパティは、省略可能なプロパティ (または省略可能な引数) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2e518-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="2e518-113">これらは、設定可能なプロパティによって表されます。</span><span class="sxs-lookup"><span data-stu-id="2e518-113">They are represented by settable properties.</span></span> <span data-ttu-id="2e518-114">コンパイラは、属性が適用されるときにこれらのプロパティを設定するための特別な構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="2e518-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="2e518-115">たとえば、<xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> プロパティは省略可能な引数を表します。</span><span class="sxs-lookup"><span data-stu-id="2e518-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>

 <span data-ttu-id="2e518-116">カスタム属性クラスに "Attribute" というサフィックスを付ける✔️ます。</span><span class="sxs-lookup"><span data-stu-id="2e518-116">✔️ DO name custom attribute classes with the suffix "Attribute."</span></span>

 <span data-ttu-id="2e518-117">✔️、<xref:System.AttributeUsageAttribute> をカスタム属性に適用します。</span><span class="sxs-lookup"><span data-stu-id="2e518-117">✔️ DO apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>

 <span data-ttu-id="2e518-118">✔️オプションの引数に設定可能なプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e518-118">✔️ DO provide settable properties for optional arguments.</span></span>

 <span data-ttu-id="2e518-119">✔️は、必須の引数の取得専用プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="2e518-119">✔️ DO provide get-only properties for required arguments.</span></span>

 <span data-ttu-id="2e518-120">必須の引数に対応するプロパティを初期化するには、コンストラクターパラメーターを指定✔️ます。</span><span class="sxs-lookup"><span data-stu-id="2e518-120">✔️ DO provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="2e518-121">各パラメーターには、対応するプロパティと同じ名前 (大文字と小文字が異なる) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e518-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>

 <span data-ttu-id="2e518-122">❌、オプションの引数に対応するプロパティを初期化するコンストラクターパラメーターを指定しないようにします。</span><span class="sxs-lookup"><span data-stu-id="2e518-122">❌ AVOID providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>

 <span data-ttu-id="2e518-123">つまり、コンストラクターとセッターの両方で設定できるプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="2e518-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="2e518-124">このガイドラインでは、省略可能な引数と必須の引数を明確に指定します。これにより、2つの方法で同じことを行うことが回避されます。</span><span class="sxs-lookup"><span data-stu-id="2e518-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>

 <span data-ttu-id="2e518-125">❌ カスタム属性コンストラクターのオーバーロードを回避します。</span><span class="sxs-lookup"><span data-stu-id="2e518-125">❌ AVOID overloading custom attribute constructors.</span></span>

 <span data-ttu-id="2e518-126">コンストラクターが1つだけの場合は、どの引数が必須であり、省略可能であるかをユーザーに明確に伝えます。</span><span class="sxs-lookup"><span data-stu-id="2e518-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>

 <span data-ttu-id="2e518-127">可能であれば、カスタム属性クラスを封印✔️ます。</span><span class="sxs-lookup"><span data-stu-id="2e518-127">✔️ DO seal custom attribute classes, if possible.</span></span> <span data-ttu-id="2e518-128">これにより、属性の参照が高速になります。</span><span class="sxs-lookup"><span data-stu-id="2e518-128">This makes the look-up for the attribute faster.</span></span>

 <span data-ttu-id="2e518-129">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="2e518-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2e518-130">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="2e518-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2e518-131">参照</span><span class="sxs-lookup"><span data-stu-id="2e518-131">See also</span></span>

- [<span data-ttu-id="2e518-132">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="2e518-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="2e518-133">使用方法のガイドライン</span><span class="sxs-lookup"><span data-stu-id="2e518-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
