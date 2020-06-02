---
title: 属性
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: 12a67d75a5f9642408cca69b2e3764a67f101549
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280583"
---
# <a name="attributes"></a><span data-ttu-id="ee388-102">属性</span><span class="sxs-lookup"><span data-stu-id="ee388-102">Attributes</span></span>

<span data-ttu-id="ee388-103"><xref:System.Attribute?displayProperty=nameWithType>は、カスタム属性を定義するために使用される基本クラスです。</span><span class="sxs-lookup"><span data-stu-id="ee388-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>

 <span data-ttu-id="ee388-104">属性は、アセンブリ、型、メンバー、パラメーターなどのプログラミング要素に追加できる注釈です。</span><span class="sxs-lookup"><span data-stu-id="ee388-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="ee388-105">これらは、アセンブリのメタデータに格納され、実行時にリフレクション Api を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ee388-105">They are stored in the metadata of the assembly and can be accessed at run time using the reflection APIs.</span></span> <span data-ttu-id="ee388-106">たとえば、.NET では、型またはメンバー <xref:System.ObsoleteAttribute> に適用できる属性を定義して、型またはメンバーが非推奨とされたことを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="ee388-106">For example, .NET defines the <xref:System.ObsoleteAttribute> attribute, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>

 <span data-ttu-id="ee388-107">属性には、属性に関連する追加データを格納する1つ以上のプロパティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ee388-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="ee388-108">たとえば、は、 `ObsoleteAttribute` 型またはメンバーが非推奨とされたリリースに関する追加情報を伝達し、古い api を置き換える新しい api の説明を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ee388-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and a description of the new API that replaces the obsolete API.</span></span>

 <span data-ttu-id="ee388-109">属性を適用するときは、属性の一部のプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee388-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="ee388-110">これらは、位置指定コンストラクターパラメーターとして表現されるため、必須プロパティまたは必須の引数と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ee388-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="ee388-111">たとえば、 <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> のプロパティ <xref:System.Diagnostics.ConditionalAttribute> は必須プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ee388-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>

 <span data-ttu-id="ee388-112">属性が適用されるときに必ずしも指定する必要がないプロパティは、省略可能なプロパティ (または省略可能な引数) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ee388-112">Properties that don't necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="ee388-113">これらは、設定可能なプロパティによって表されます。</span><span class="sxs-lookup"><span data-stu-id="ee388-113">They are represented by settable properties.</span></span> <span data-ttu-id="ee388-114">コンパイラは、属性が適用されるときにこれらのプロパティを設定するための特別な構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="ee388-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="ee388-115">たとえば、プロパティは <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 省略可能な引数を表します。</span><span class="sxs-lookup"><span data-stu-id="ee388-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>

 <span data-ttu-id="ee388-116">カスタム属性クラスに "Attribute" というサフィックスを付ける✔️ます。</span><span class="sxs-lookup"><span data-stu-id="ee388-116">✔️ DO name custom attribute classes with the suffix "Attribute."</span></span>

 <span data-ttu-id="ee388-117">✔️ <xref:System.AttributeUsageAttribute> カスタム属性に適用します。</span><span class="sxs-lookup"><span data-stu-id="ee388-117">✔️ DO apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>

 <span data-ttu-id="ee388-118">✔️オプションの引数に設定可能なプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee388-118">✔️ DO provide settable properties for optional arguments.</span></span>

 <span data-ttu-id="ee388-119">✔️は、必須の引数の取得専用プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="ee388-119">✔️ DO provide get-only properties for required arguments.</span></span>

 <span data-ttu-id="ee388-120">必須の引数に対応するプロパティを初期化するには、コンストラクターパラメーターを指定✔️ます。</span><span class="sxs-lookup"><span data-stu-id="ee388-120">✔️ DO provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="ee388-121">各パラメーターには、対応するプロパティと同じ名前 (大文字と小文字が異なる) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee388-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>

 <span data-ttu-id="ee388-122">❌省略可能な引数に対応するプロパティを初期化するコンストラクターパラメーターを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="ee388-122">❌ AVOID providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>

 <span data-ttu-id="ee388-123">つまり、コンストラクターとセッターの両方で設定できるプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="ee388-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="ee388-124">このガイドラインでは、省略可能な引数と必須の引数を明確に指定します。これにより、2つの方法で同じことを行うことが回避されます。</span><span class="sxs-lookup"><span data-stu-id="ee388-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>

 <span data-ttu-id="ee388-125">❌カスタム属性コンストラクターのオーバーロードは避けてください。</span><span class="sxs-lookup"><span data-stu-id="ee388-125">❌ AVOID overloading custom attribute constructors.</span></span>

 <span data-ttu-id="ee388-126">コンストラクターが1つだけの場合は、どの引数が必須であり、省略可能であるかをユーザーに明確に伝えます。</span><span class="sxs-lookup"><span data-stu-id="ee388-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>

 <span data-ttu-id="ee388-127">可能であれば、カスタム属性クラスを封印✔️ます。</span><span class="sxs-lookup"><span data-stu-id="ee388-127">✔️ DO seal custom attribute classes, if possible.</span></span> <span data-ttu-id="ee388-128">これにより、属性の参照が高速になります。</span><span class="sxs-lookup"><span data-stu-id="ee388-128">This makes the look-up for the attribute faster.</span></span>

 <span data-ttu-id="ee388-129">*部分 &copy; 2005、2009 Microsoft Corporation。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="ee388-129">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ee388-130">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="ee388-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ee388-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee388-131">See also</span></span>

- [<span data-ttu-id="ee388-132">フレームワークデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="ee388-132">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="ee388-133">使用に関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="ee388-133">Usage Guidelines</span></span>](usage-guidelines.md)
