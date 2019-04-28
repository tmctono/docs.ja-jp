---
title: 入れ子にされた型
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: KrzysztofCwalina
ms.openlocfilehash: 22c14d05105154ff642cb8a44eda8e7c5d0575e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756872"
---
# <a name="nested-types"></a><span data-ttu-id="77e32-102">入れ子にされた型</span><span class="sxs-lookup"><span data-stu-id="77e32-102">Nested Types</span></span>
<span data-ttu-id="77e32-103">入れ子になった型は、それを囲む型と呼ばれる別の型のスコープ内で定義されている型です。</span><span class="sxs-lookup"><span data-stu-id="77e32-103">A nested type is a type defined within the scope of another type, which is called the enclosing type.</span></span> <span data-ttu-id="77e32-104">入れ子にされた型が、その外側の型のすべてのメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="77e32-104">A nested type has access to all members of its enclosing type.</span></span> <span data-ttu-id="77e32-105">たとえば、それを囲む型のすべての先祖で定義されているフィールドを保護して、外側の型で定義されてプライベート フィールドにアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="77e32-105">For example, it has access to private fields defined in the enclosing type and to protected fields defined in all ascendants of the enclosing type.</span></span>  
  
 <span data-ttu-id="77e32-106">一般に、控えめ入れ子にされた型に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e32-106">In general, nested types should be used sparingly.</span></span> <span data-ttu-id="77e32-107">直接呼び出すべきではないいくつかの理由があります。</span><span class="sxs-lookup"><span data-stu-id="77e32-107">There are several reasons for this.</span></span> <span data-ttu-id="77e32-108">一部の開発者の概念を熟知していません。</span><span class="sxs-lookup"><span data-stu-id="77e32-108">Some developers are not fully familiar with the concept.</span></span> <span data-ttu-id="77e32-109">これらの開発者では、入れ子にされた型の変数の宣言の構文に問題があるなどがあります。</span><span class="sxs-lookup"><span data-stu-id="77e32-109">These developers might, for example, have problems with the syntax of declaring variables of nested types.</span></span> <span data-ttu-id="77e32-110">入れ子にされた型は、その外側の型でも非常に緊密に結合されていて、そのため、汎用型であることには適していません。</span><span class="sxs-lookup"><span data-stu-id="77e32-110">Nested types are also very tightly coupled with their enclosing types, and as such are not suited to be general-purpose types.</span></span>  
  
 <span data-ttu-id="77e32-111">入れ子にされた型は、それを囲む型の実装の詳細をモデル化するために最適です。</span><span class="sxs-lookup"><span data-stu-id="77e32-111">Nested types are best suited for modeling implementation details of their enclosing types.</span></span> <span data-ttu-id="77e32-112">エンドユーザーは、入れ子にされた型の変数を宣言する必要はほとんどとほとんどない、入れ子にされた型を明示的にインスタンス化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e32-112">The end user should rarely have to declare variables of a nested type and almost never should have to explicitly instantiate nested types.</span></span> <span data-ttu-id="77e32-113">たとえば、コレクションの列挙子は、そのコレクションの入れ子にされた型にできます。</span><span class="sxs-lookup"><span data-stu-id="77e32-113">For example, the enumerator of a collection can be a nested type of that collection.</span></span> <span data-ttu-id="77e32-114">列挙子がその外側の型でインスタンス化は、通常、列挙子変数に、エンドユーザーが宣言することはほとんどありませんがあるため、多くの言語では、foreach ステートメントをサポート、.</span><span class="sxs-lookup"><span data-stu-id="77e32-114">Enumerators are usually instantiated by their enclosing type, and because many languages support the foreach statement, enumerator variables rarely have to be declared by the end user.</span></span>  
  
 <span data-ttu-id="77e32-115">**✓ DO** 入れ子にされた型とその外側の型間の関係のあるメンバーのアクセシビリティのセマンティクスは次のことをお勧めときに、入れ子にされた型を使用します。</span><span class="sxs-lookup"><span data-stu-id="77e32-115">**✓ DO** use nested types when the relationship between the nested type and its outer type is such that member-accessibility semantics are desirable.</span></span>  
  
 <span data-ttu-id="77e32-116">**X DO NOT** 論理的なグループとしてパブリック入れ子にされた型を使用して構築以外の場合はこの名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="77e32-116">**X DO NOT** use public nested types as a logical grouping construct; use namespaces for this.</span></span>  
  
 <span data-ttu-id="77e32-117">**X AVOID** 入れ子にされた型をパブリックに公開します。</span><span class="sxs-lookup"><span data-stu-id="77e32-117">**X AVOID** publicly exposed nested types.</span></span> <span data-ttu-id="77e32-118">唯一の例外は、入れ子にされた型の変数をサブクラスまたはその他の高度なカスタマイズ シナリオなどのまれなシナリオでのみ宣言する必要があるかどうかです。</span><span class="sxs-lookup"><span data-stu-id="77e32-118">The only exception to this is if variables of the nested type need to be declared only in rare scenarios such as subclassing or other advanced customization scenarios.</span></span>  
  
 <span data-ttu-id="77e32-119">**X DO NOT** 型が、含んでいる型の外部で参照されている可能性が高い場合は、入れ子にされた型を使用します。</span><span class="sxs-lookup"><span data-stu-id="77e32-119">**X DO NOT** use nested types if the type is likely to be referenced outside of the containing type.</span></span>  
  
 <span data-ttu-id="77e32-120">たとえば、クラスで定義されたメソッドに渡される列挙型はクラスの入れ子にされた型として定義されませんする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e32-120">For example, an enum passed to a method defined on a class should not be defined as a nested type in the class.</span></span>  
  
 <span data-ttu-id="77e32-121">**X DO NOT** クライアント コードでインスタンス化する必要がある場合は、入れ子にされた型を使用します。</span><span class="sxs-lookup"><span data-stu-id="77e32-121">**X DO NOT** use nested types if they need to be instantiated by client code.</span></span>  <span data-ttu-id="77e32-122">型のパブリック コンス トラクターの場合する必要がありますネストいない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="77e32-122">If a type has a public constructor, it should probably not be nested.</span></span>  
  
 <span data-ttu-id="77e32-123">型が、独自のフレームワーク内の場所を示すために思えます型をインスタンス化する場合 (できます作成し、それに伴う作業し、これまで、外部型を使用せず、それを破棄)、そのため、ネストいない必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e32-123">If a type can be instantiated, that seems to indicate the type has a place in the framework on its own (you can create it, work with it, and destroy it without ever using the outer type), and thus should not be nested.</span></span> <span data-ttu-id="77e32-124">内部型する必要がありますいない広範囲に再利用、リレーションシップがない場合は、外側の型の外部で外側の型にもします。</span><span class="sxs-lookup"><span data-stu-id="77e32-124">Inner types should not be widely reused outside of the outer type without any relationship whatsoever to the outer type.</span></span>  
  
 <span data-ttu-id="77e32-125">**X DO NOT** インターフェイスのメンバーとして入れ子にされた型を定義します。</span><span class="sxs-lookup"><span data-stu-id="77e32-125">**X DO NOT** define a nested type as a member of an interface.</span></span> <span data-ttu-id="77e32-126">多くの言語は、そのようなコンストラクトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="77e32-126">Many languages do not support such a construct.</span></span>  
  
 <span data-ttu-id="77e32-127">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="77e32-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="77e32-128">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="77e32-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e32-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="77e32-129">See also</span></span>

- [<span data-ttu-id="77e32-130">型デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="77e32-130">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="77e32-131">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="77e32-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
