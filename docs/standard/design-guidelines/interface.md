---
title: インターフェイスのデザイン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: f589d47d5b945179430275598996b2fb77e92848
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289032"
---
# <a name="interface-design"></a><span data-ttu-id="a3bed-102">インターフェイスのデザイン</span><span class="sxs-lookup"><span data-stu-id="a3bed-102">Interface Design</span></span>
<span data-ttu-id="a3bed-103">ほとんどの Api はクラスと構造体を使用してモデル化されていますが、インターフェイスがより適している場合や、唯一のオプションである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a3bed-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>

 <span data-ttu-id="a3bed-104">CLR は複数の継承をサポートしていません (つまり、CLR クラスは複数の基底クラスから継承することはできません) が、基底クラスから継承するだけでなく、1つまたは複数のインターフェイスを実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3bed-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="a3bed-105">したがって、多くの場合、インターフェイスは、多重継承の効果を実現するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3bed-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="a3bed-106">たとえば、 <xref:System.IDisposable> は、参加する他の継承階層に依存しない disposability をサポートする型を許可するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="a3bed-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>

 <span data-ttu-id="a3bed-107">インターフェイスを定義する他の状況としては、いくつかの値型を含む、複数の型でサポートできる共通インターフェイスを作成することがあります。</span><span class="sxs-lookup"><span data-stu-id="a3bed-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="a3bed-108">値型は以外の型から継承することはできません <xref:System.ValueType> が、インターフェイスを実装することはできます。そのため、共通の基本型を指定するための唯一のオプションはインターフェイスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="a3bed-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>

 <span data-ttu-id="a3bed-109">値の型を含む型のセットによってサポートされる共通 API が必要な場合は、インターフェイスを定義✔️ます。</span><span class="sxs-lookup"><span data-stu-id="a3bed-109">✔️ DO define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>

 <span data-ttu-id="a3bed-110">他の型から既に継承されている型で機能をサポートする必要がある場合は、インターフェイスを定義することを✔️してください。</span><span class="sxs-lookup"><span data-stu-id="a3bed-110">✔️ CONSIDER defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>

 <span data-ttu-id="a3bed-111">❌マーカーインターフェイス (メンバーのないインターフェイス) は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3bed-111">❌ AVOID using marker interfaces (interfaces with no members).</span></span>

 <span data-ttu-id="a3bed-112">クラスを特定の特性 (マーカー) としてマークする必要がある場合は、一般に、インターフェイスではなくカスタム属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3bed-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>

 <span data-ttu-id="a3bed-113">✔️インターフェイスの実装である型を少なくとも1つ指定してください。</span><span class="sxs-lookup"><span data-stu-id="a3bed-113">✔️ DO provide at least one type that is an implementation of an interface.</span></span>

 <span data-ttu-id="a3bed-114">これにより、インターフェイスの設計を検証できます。</span><span class="sxs-lookup"><span data-stu-id="a3bed-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="a3bed-115">たとえば、 <xref:System.Collections.Generic.List%601> はインターフェイスの実装です <xref:System.Collections.Generic.IList%601> 。</span><span class="sxs-lookup"><span data-stu-id="a3bed-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>

 <span data-ttu-id="a3bed-116">定義した各インターフェイスを使用する API を少なくとも1つ (パラメーターとして、またはインターフェイスとして型指定されたプロパティとして受け取るメソッド) を指定✔️ます。</span><span class="sxs-lookup"><span data-stu-id="a3bed-116">✔️ DO provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>

 <span data-ttu-id="a3bed-117">これにより、インターフェイスの設計を検証できます。</span><span class="sxs-lookup"><span data-stu-id="a3bed-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="a3bed-118">たとえば、は <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> インターフェイスを使用し <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="a3bed-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>

 <span data-ttu-id="a3bed-119">❌以前に出荷されたインターフェイスにメンバーを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3bed-119">❌ DO NOT add members to an interface that has previously shipped.</span></span>

 <span data-ttu-id="a3bed-120">これにより、インターフェイスの実装が中断されます。</span><span class="sxs-lookup"><span data-stu-id="a3bed-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="a3bed-121">バージョン管理の問題を回避するために、新しいインターフェイスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3bed-121">You should create a new interface in order to avoid versioning problems.</span></span>

 <span data-ttu-id="a3bed-122">これらのガイドラインで説明されている状況を除き、一般に、マネージコードの再利用可能なライブラリの設計では、インターフェイスではなくクラスを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3bed-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>

 <span data-ttu-id="a3bed-123">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="a3bed-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a3bed-124">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="a3bed-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a3bed-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3bed-125">See also</span></span>

- [<span data-ttu-id="a3bed-126">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a3bed-126">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="a3bed-127">フレームワークデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a3bed-127">Framework Design Guidelines</span></span>](index.md)
