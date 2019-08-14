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
author: KrzysztofCwalina
ms.openlocfilehash: f9fe3045d8bd8b4d625c5cd49bc18574ebb740de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026433"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="6501d-102">例外とパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="6501d-102">Exceptions and Performance</span></span>
<span data-ttu-id="6501d-103">例外に関連する一般的な懸念事項の 1 つを定期的に失敗したコードの例外を使用している場合、パフォーマンスの実装は受け入れられない。</span><span class="sxs-lookup"><span data-stu-id="6501d-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="6501d-104">これはもっともです。</span><span class="sxs-lookup"><span data-stu-id="6501d-104">This is a valid concern.</span></span> <span data-ttu-id="6501d-105">メンバーは、例外をスローするときに、パフォーマンスが極端に遅くにできます。</span><span class="sxs-lookup"><span data-stu-id="6501d-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="6501d-106">ただし、エラー コードの使用を禁止する例外のガイドラインに厳密に準拠しつつ、良好なパフォーマンスを実現することができます。</span><span class="sxs-lookup"><span data-stu-id="6501d-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="6501d-107">このセクションで説明されている 2 つのパターンは、これを行う方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6501d-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="6501d-108">**X DO NOT** 例外がパフォーマンスに悪影響を及ぼす影響する問題が原因のエラー コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6501d-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="6501d-109">パフォーマンスを向上させるのには、Tester-doer パターンまたは解析を試行パターンは、次の 2 つのセクションで説明されているかを使用して、します。</span><span class="sxs-lookup"><span data-stu-id="6501d-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="6501d-110">Tester-doer パターン</span><span class="sxs-lookup"><span data-stu-id="6501d-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="6501d-111">場合があります、メンバーを 2 つに分割することにより、例外のスローのメンバーのパフォーマンスが向上することができます。</span><span class="sxs-lookup"><span data-stu-id="6501d-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="6501d-112">見て、<xref:System.Collections.Generic.ICollection%601.Add%2A>のメソッド、<xref:System.Collections.Generic.ICollection%601>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6501d-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="6501d-113">メソッド`Add`コレクションが読み取り専用の場合にスローします。</span><span class="sxs-lookup"><span data-stu-id="6501d-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="6501d-114">これは、メソッドの呼び出しが失敗する多くの場合に必要な場合のシナリオでパフォーマンスの問題です。</span><span class="sxs-lookup"><span data-stu-id="6501d-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="6501d-115">値を追加する前に、コレクションが書き込み可能かどうかをテストすると、問題を軽減する方法のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6501d-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="6501d-116">この例では、プロパティを条件をテストするために使用するメンバー `IsReadOnly`、テスト担当者と呼びます。</span><span class="sxs-lookup"><span data-stu-id="6501d-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="6501d-117">スロー可能性のある操作を実行するために使用するメンバー、`Add`例では、メソッドは、渡ってと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6501d-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="6501d-118">**✓ CONSIDER** Tester 渡ってパターンが例外をスローするメンバーの共通のパフォーマンスの問題を回避するシナリオに関連する例外。</span><span class="sxs-lookup"><span data-stu-id="6501d-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="6501d-119">解析を試行パターン</span><span class="sxs-lookup"><span data-stu-id="6501d-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="6501d-120">非常にパフォーマンスが重視される api の場合は、前のセクションで説明されている Tester-doer パターンよりもさらに高速のパターンを使用してください。</span><span class="sxs-lookup"><span data-stu-id="6501d-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="6501d-121">メンバーのセマンティクスの一部の場合、適切に定義されたテストを作成するメンバーの名前を調整するためのパターンを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6501d-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="6501d-122">たとえば、<xref:System.DateTime>定義、<xref:System.DateTime.Parse%2A>文字列の解析に失敗した場合に例外をスローするメソッド。</span><span class="sxs-lookup"><span data-stu-id="6501d-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="6501d-123">対応する定義も<xref:System.DateTime.TryParse%2A>を解析しようとするメソッドが false を返します解析が失敗し、正常に解析を使用して、結果を返す場合、`out`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="6501d-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 <span data-ttu-id="6501d-124">このパターンを使用する場合は、厳密な用語で try 機能を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6501d-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="6501d-125">メンバーに適切に定義された try 以外の何らかの理由で失敗した場合、メンバーが対応する例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6501d-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="6501d-126">**✓ CONSIDER** Try 解析パターンが例外をスローするメンバーの共通のパフォーマンスの問題を回避するシナリオに関連する例外。</span><span class="sxs-lookup"><span data-stu-id="6501d-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="6501d-127">**✓ DO** このパターンを実装するメソッドにプレフィックス"Try"とブール型の戻り値の型を使用します。</span><span class="sxs-lookup"><span data-stu-id="6501d-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="6501d-128">**✓ DO** Try 解析パターンを使用する各メンバーに対して例外スローのメンバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="6501d-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="6501d-129">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="6501d-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6501d-130">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="6501d-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6501d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="6501d-131">See also</span></span>

- [<span data-ttu-id="6501d-132">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="6501d-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="6501d-133">例外のデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="6501d-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
