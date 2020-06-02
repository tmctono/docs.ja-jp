---
title: 例外とパフォーマンス
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: a558547f0e6770e7e76ca31f760d6e2f55c712db
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289786"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="20a4b-102">例外とパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="20a4b-102">Exceptions and Performance</span></span>
<span data-ttu-id="20a4b-103">例外に関する一般的な懸念事項の1つとして、定期的に失敗するコードに例外を使用すると、実装のパフォーマンスが許容されなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="20a4b-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="20a4b-104">これは有効な問題です。</span><span class="sxs-lookup"><span data-stu-id="20a4b-104">This is a valid concern.</span></span> <span data-ttu-id="20a4b-105">メンバーが例外をスローすると、パフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="20a4b-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="20a4b-106">ただし、エラーコードの使用を禁止する例外ガイドラインに厳密に準拠しながら、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="20a4b-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="20a4b-107">このセクションで説明する2つのパターンは、この方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="20a4b-107">Two patterns described in this section suggest ways to do this.</span></span>

 <span data-ttu-id="20a4b-108">❌エラーコードは、例外がパフォーマンスに悪影響を与える可能性があるため、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="20a4b-108">❌ DO NOT use error codes because of concerns that exceptions might affect performance negatively.</span></span>

 <span data-ttu-id="20a4b-109">パフォーマンスを向上させるために、次の2つのセクションで説明するように、テスト担当者またはテスト用のパターンを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="20a4b-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>

## <a name="tester-doer-pattern"></a><span data-ttu-id="20a4b-110">テスト担当者-Doer パターン</span><span class="sxs-lookup"><span data-stu-id="20a4b-110">Tester-Doer Pattern</span></span>
 <span data-ttu-id="20a4b-111">メンバーを2つに分割すると、例外スローメンバーのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="20a4b-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="20a4b-112">では、インターフェイスのメソッドを見てみましょう <xref:System.Collections.Generic.ICollection%601.Add%2A> <xref:System.Collections.Generic.ICollection%601> 。</span><span class="sxs-lookup"><span data-stu-id="20a4b-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 <span data-ttu-id="20a4b-113">コレクションが読み取り専用の場合、メソッドはを `Add` スローします。</span><span class="sxs-lookup"><span data-stu-id="20a4b-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="20a4b-114">これは、メソッドの呼び出しが頻繁に失敗することが予想されるシナリオでパフォーマンスの問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20a4b-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="20a4b-115">問題を軽減する方法の1つは、値を追加する前に、コレクションが書き込み可能かどうかをテストすることです。</span><span class="sxs-lookup"><span data-stu-id="20a4b-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 <span data-ttu-id="20a4b-116">条件をテストするために使用されるメンバー (この例ではプロパティ) は、テスト `IsReadOnly` 担当者と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="20a4b-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="20a4b-117">スローされる可能性のある操作を実行するために使用するメンバーは、この `Add` 例のメソッドを doer と呼びます。</span><span class="sxs-lookup"><span data-stu-id="20a4b-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>

 <span data-ttu-id="20a4b-118">✔️、例外に関連するパフォーマンスの問題を回避するために、一般的なシナリオで例外をスローする可能性のあるメンバーに対してテスト担当者のパターンを検討してください。</span><span class="sxs-lookup"><span data-stu-id="20a4b-118">✔️ CONSIDER the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

## <a name="try-parse-pattern"></a><span data-ttu-id="20a4b-119">Try 解析パターン</span><span class="sxs-lookup"><span data-stu-id="20a4b-119">Try-Parse Pattern</span></span>
 <span data-ttu-id="20a4b-120">パフォーマンスが非常に重要な Api では、前のセクションで説明したテスト担当者のパターンよりも高速なパターンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20a4b-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="20a4b-121">このパターンでは、メンバー名を調整して、適切に定義されたテストケースをメンバーセマンティクスの一部にするためのを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="20a4b-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="20a4b-122">たとえば、は、 <xref:System.DateTime> <xref:System.DateTime.Parse%2A> 文字列の解析が失敗した場合に例外をスローするメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="20a4b-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="20a4b-123">また、解析を試行する対応するメソッドも定義 <xref:System.DateTime.TryParse%2A> しますが、解析が失敗した場合は false を返し、パラメーターを使用して解析の成功の結果を返し `out` ます。</span><span class="sxs-lookup"><span data-stu-id="20a4b-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 <span data-ttu-id="20a4b-124">このパターンを使用する場合は、厳密な用語で try 機能を定義することが重要です。</span><span class="sxs-lookup"><span data-stu-id="20a4b-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="20a4b-125">明確に定義された try 以外の理由でメンバーが失敗した場合でも、メンバーは対応する例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20a4b-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>

 <span data-ttu-id="20a4b-126">✔️、例外に関連するパフォーマンスの問題を回避するために、一般的なシナリオで例外をスローする可能性のあるメンバーのために、Try 解析パターンを検討してください。</span><span class="sxs-lookup"><span data-stu-id="20a4b-126">✔️ CONSIDER the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

 <span data-ttu-id="20a4b-127">このパターンを実装するメソッドには、"Try" というプレフィックスとブール型の戻り値の型を使用✔️ます。</span><span class="sxs-lookup"><span data-stu-id="20a4b-127">✔️ DO use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>

 <span data-ttu-id="20a4b-128">✔️、Try 解析パターンを使用して、メンバーごとに例外スローメンバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="20a4b-128">✔️ DO provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>

 <span data-ttu-id="20a4b-129">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="20a4b-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="20a4b-130">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="20a4b-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="20a4b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="20a4b-131">See also</span></span>

- [<span data-ttu-id="20a4b-132">フレームワークデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="20a4b-132">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="20a4b-133">例外のデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="20a4b-133">Design Guidelines for Exceptions</span></span>](exceptions.md)
