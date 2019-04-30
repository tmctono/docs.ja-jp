---
title: プロパティのデザイン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
author: KrzysztofCwalina
ms.openlocfilehash: e4ed4fd39a9ebd63b9d5dbff38dc15647d65934f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026311"
---
# <a name="property-design"></a><span data-ttu-id="d69fe-102">プロパティのデザイン</span><span class="sxs-lookup"><span data-stu-id="d69fe-102">Property Design</span></span>
<span data-ttu-id="d69fe-103">プロパティはメソッドに厳密にはよく似ていますは、使用シナリオの観点からはまったく異なります。</span><span class="sxs-lookup"><span data-stu-id="d69fe-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="d69fe-104">これらは、スマート フィールドとして認識する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d69fe-104">They should be seen as smart fields.</span></span> <span data-ttu-id="d69fe-105">呼び出し元のフィールドの構文とメソッドの柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="d69fe-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="d69fe-106">**✓ DO** 呼び出し元が、プロパティの値を変更すべき場合取得専用のプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="d69fe-107">留意している場合の種類、プロパティが変更可能な参照型、プロパティが取得専用の場合でも、プロパティの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d69fe-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="d69fe-108">**X DO NOT** 設定専用のプロパティまたはプロパティを get アクセス操作子よりも広範なアクセシビリティを持つ set アクセス操作子を提供します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="d69fe-109">たとえば、パブリック セッターと保護された getter プロパティは使用しないでいます。</span><span class="sxs-lookup"><span data-stu-id="d69fe-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="d69fe-110">プロパティの get アクセス操作子を提供できない場合は、メソッドと機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="d69fe-111">メソッド名の開始を検討してください`Set`し、何が名前を付けているプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d69fe-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="d69fe-112">たとえば、<xref:System.AppDomain>というメソッドを持ち`SetCachePath`と呼ばれる設定専用のプロパティではなく`CachePath`します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="d69fe-113">**✓ DO** 既定の設定がセキュリティ ホールや重大な非効率的なコードで発生しないようにする、すべてのプロパティの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="d69fe-114">**✓ DO** 場合でも、この結果、オブジェクトの一時的な無効な状態で、任意の順序で設定するプロパティを許可します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="d69fe-115">同じオブジェクトの他のプロパティの値が指定の 2 つ以上のプロパティをいくつかの値を 1 つのプロパティの無効になるポイントを相互に関連する一般的です。</span><span class="sxs-lookup"><span data-stu-id="d69fe-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="d69fe-116">このような場合、オブジェクトによって、相互に関連するプロパティをまとめて使用実際になるまで無効な状態に起因する例外を延期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d69fe-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="d69fe-117">**✓ DO** プロパティ set アクセス操作子は例外をスローする場合は、以前の値を保持します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="d69fe-118">**X AVOID** プロパティ get アクセス操作子から例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="d69fe-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="d69fe-119">プロパティの getter は、単純な操作をする必要があり、すべての前提条件はありません。</span><span class="sxs-lookup"><span data-stu-id="d69fe-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="d69fe-120">Getter は、例外をスローできます、メソッドに設計おそらく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d69fe-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="d69fe-121">このルールが、引数の検証の結果として例外を予定はインデクサーに適用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d69fe-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="d69fe-122">インデックス付きプロパティのデザイン</span><span class="sxs-lookup"><span data-stu-id="d69fe-122">Indexed Property Design</span></span>  
 <span data-ttu-id="d69fe-123">インデックス付きプロパティは、パラメーターを持つことができますし、配列のインデックスのような特別な構文で呼び出せる特別なプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d69fe-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="d69fe-124">インデックス付きプロパティは、インデクサーとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d69fe-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="d69fe-125">インデクサーは、論理コレクション内の項目へのアクセスを提供する Api でのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d69fe-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="d69fe-126">たとえば、文字列は、一連の文字、およびインデクサーを<xref:System.String?displayProperty=nameWithType>その文字にアクセスするようになりました。</span><span class="sxs-lookup"><span data-stu-id="d69fe-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="d69fe-127">**✓ CONSIDER** 内部配列に格納されたデータへのアクセスを提供するインデクサーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="d69fe-128">**✓ CONSIDER** 項目のコレクションを表す型のインデクサーを提供します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="d69fe-129">**X AVOID** 1 つ以上のパラメーターを持つプロパティを使用してインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="d69fe-130">設計には、複数のパラメーターが必要とする場合は、プロパティは本当に論理的なコレクションにアクセサーを表すかどうかを再確認します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="d69fe-131">そうでない場合は、代わりにメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-131">If it does not, use methods instead.</span></span> <span data-ttu-id="d69fe-132">メソッド名の開始を検討してください`Get`または`Set`します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="d69fe-133">**X AVOID** 以外のパラメーターの型を持つインデクサー <xref:System.Int32?displayProperty=nameWithType>、 <xref:System.Int64?displayProperty=nameWithType>、 <xref:System.String?displayProperty=nameWithType>、 <xref:System.Object?displayProperty=nameWithType>、または列挙型。</span><span class="sxs-lookup"><span data-stu-id="d69fe-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="d69fe-134">設計には、他の種類のパラメーターが必要とする場合は、厳密に API が論理的なコレクションに実際にアクセサーを表すかどうかを再評価します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="d69fe-135">そうでない場合は、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-135">If it does not, use a method.</span></span> <span data-ttu-id="d69fe-136">メソッド名の開始を検討してください`Get`または`Set`します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="d69fe-137">**✓ DO** 名前を使用して`Item`の言うまでもなく、名前がある場合を除き、インデックス付きプロパティ (などを参照してください、<xref:System.String.Chars%2A>プロパティを`System.String`)。</span><span class="sxs-lookup"><span data-stu-id="d69fe-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="d69fe-138">C# では、インデクサーは、既定の項目の名前は。</span><span class="sxs-lookup"><span data-stu-id="d69fe-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="d69fe-139"><xref:System.Runtime.CompilerServices.IndexerNameAttribute>この名前をカスタマイズするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d69fe-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="d69fe-140">**X DO NOT** インデクサーと意味的に等しいメソッドの両方を提供します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="d69fe-141">**X DO NOT** 1 つの型でのオーバー ロードされたインデクサーの 1 つ以上のファミリを指定します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="d69fe-142">これは、c# コンパイラによって強制されます。</span><span class="sxs-lookup"><span data-stu-id="d69fe-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="d69fe-143">**X DO NOT** 使用する既定以外のインデックス付きプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d69fe-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="d69fe-144">これは、c# コンパイラによって強制されます。</span><span class="sxs-lookup"><span data-stu-id="d69fe-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="d69fe-145">プロパティ変更通知イベント</span><span class="sxs-lookup"><span data-stu-id="d69fe-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="d69fe-146">プロパティ値の変更のユーザーに通知するイベントを提供する便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d69fe-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="d69fe-147">たとえば、`System.Windows.Forms.Control`を発生させます、`TextChanged`イベントの値の後にその`Text`プロパティが変更されました。</span><span class="sxs-lookup"><span data-stu-id="d69fe-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="d69fe-148">**✓ CONSIDER** 大まかな Api (通常、デザイナー コンポーネント) のプロパティ値が変更されたときに通知イベントを変更させるとします。</span><span class="sxs-lookup"><span data-stu-id="d69fe-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="d69fe-149">ユーザーがオブジェクトのプロパティを変更する場合を判断するに適したシナリオがある場合、オブジェクトは、プロパティの変更通知イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="d69fe-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="d69fe-150">ただし、オーバーヘッドの基本型やコレクションなどの低レベルの Api のようなイベントを発生させるのには価値がある可能性がありますはありません。</span><span class="sxs-lookup"><span data-stu-id="d69fe-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="d69fe-151">たとえば、<xref:System.Collections.Generic.List%601>一覧に新しい項目が追加されたときに、このようなイベントが発生しないと、`Count`プロパティの変更。</span><span class="sxs-lookup"><span data-stu-id="d69fe-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="d69fe-152">**✓ CONSIDER** 外的要因を使用して、プロパティの値が変更されたときに、通知イベントを発生させる変更します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="d69fe-153">いくつかの外的要因 (オブジェクトのメソッドを呼び出して、以外の方法) で使用してプロパティ値が変更された場合に発生させる値が変更され、変更されたことを開発者イベントを示します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="d69fe-154">その良い例が、`Text`テキスト ボックス コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d69fe-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="d69fe-155">ユーザーがテキストで、`TextBox`プロパティの値が自動的に変更します。</span><span class="sxs-lookup"><span data-stu-id="d69fe-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="d69fe-156">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="d69fe-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d69fe-157">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="d69fe-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d69fe-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="d69fe-158">See also</span></span>

- [<span data-ttu-id="d69fe-159">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="d69fe-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="d69fe-160">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="d69fe-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
