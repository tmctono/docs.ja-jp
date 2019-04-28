---
title: Ref 戻り値 (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: d0600f7d9030324160343e800c37e0f5e68bff61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791808"
---
# <a name="support-for-reference-return-values-visual-basic"></a><span data-ttu-id="4206e-102">参照戻り値 (Visual Basic) のサポート</span><span class="sxs-lookup"><span data-stu-id="4206e-102">Support for reference return values (Visual Basic)</span></span>

<span data-ttu-id="4206e-103">以降でC#7.0 では、C#の言語サポート*戻り値の参照*します。</span><span class="sxs-lookup"><span data-stu-id="4206e-103">Starting with C# 7.0, the C# language supports *reference return values*.</span></span> <span data-ttu-id="4206e-104">参照戻り値を理解する方法の 1 つは、メソッドへの参照によって渡される引数の逆であります。</span><span class="sxs-lookup"><span data-stu-id="4206e-104">One way to understand reference return values is that they are the opposite of arguments that are passed by reference to a method.</span></span> <span data-ttu-id="4206e-105">参照によって渡された引数が変更されたときに、変更は、呼び出し元に、変数の値に反映されます。</span><span class="sxs-lookup"><span data-stu-id="4206e-105">When an argument passed by reference is modified, the changes are reflected in value of the variable on the caller.</span></span> <span data-ttu-id="4206e-106">参照戻り値を提供します、呼び出し元に、メソッドと、は、呼び出されたメソッドのデータで、呼び出し元が参照戻り値に加えられた変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="4206e-106">When an method provides a reference return value to a caller, modifications made to the reference return value by the caller are reflected in the called method's data.</span></span>

<span data-ttu-id="4206e-107">Visual Basic では、参照を持つメソッドを作成すると、戻り値が、参照戻り値を使用することは許可されません。</span><span class="sxs-lookup"><span data-stu-id="4206e-107">Visual Basic does not allow you to author methods with reference return values, but it does allow you to consume reference return values.</span></span> <span data-ttu-id="4206e-108">つまり、参照戻り値を持つメソッドを呼び出すし、その戻り値を変更し、呼び出されたメソッドのデータに参照戻り値の変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="4206e-108">In other words, you can call a method with a reference return value and modify that return value, and changes to the reference return value are reflected in the called method's data.</span></span>

## <a name="modifying-the-ref-return-value-directly"></a><span data-ttu-id="4206e-109">Ref 戻り値を直接変更します。</span><span class="sxs-lookup"><span data-stu-id="4206e-109">Modifying the ref return value directly</span></span>

<span data-ttu-id="4206e-110">常に成功し、されていないメソッドは`ByRef`パラメーター、参照戻り値を直接変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4206e-110">For methods that always succeed and have no `ByRef` parameters, you can modify the reference return value directly.</span></span> <span data-ttu-id="4206e-111">参照戻り値を返す式に新しい値を割り当てるこれを行います。</span><span class="sxs-lookup"><span data-stu-id="4206e-111">You do this by assigning the new value to the expressions that returns the reference return value.</span></span> 

<span data-ttu-id="4206e-112">次C#例、`NumericValue.IncrementValue`値を返すメソッドを内部の値をインクリメントし、参照として返します。</span><span class="sxs-lookup"><span data-stu-id="4206e-112">The following C# example defines a `NumericValue.IncrementValue` method that increments an internal value and returns it as a reference return value.</span></span> 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

<span data-ttu-id="4206e-113">参照は、Visual Basic の例を次に、呼び出し元によって値が変更を返します。</span><span class="sxs-lookup"><span data-stu-id="4206e-113">The reference return value is then modified by the caller in the following Visual Basic example.</span></span> <span data-ttu-id="4206e-114">注意では、行、`NumericValue.IncrementValue`メソッドの呼び出しでは、メソッドには、値は割り当てません。</span><span class="sxs-lookup"><span data-stu-id="4206e-114">Note that the line with the `NumericValue.IncrementValue` method call does not assign a value to the method.</span></span> <span data-ttu-id="4206e-115">代わりに、メソッドによって返される参照戻り値に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4206e-115">Instead, it assigns a value to the reference return value returned by the method.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a><span data-ttu-id="4206e-116">ヘルパー メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="4206e-116">Using a helper method</span></span>

<span data-ttu-id="4206e-117">それ以外の場合、メソッド呼び出しの参照の戻り値を直接変更常にお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="4206e-117">In other cases, modifying the reference return value of a method call directly may not always be desirable.</span></span> <span data-ttu-id="4206e-118">たとえば、文字列を返す検索メソッドが常に一致が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="4206e-118">For example, a search method that returns a string may not always find a match.</span></span> <span data-ttu-id="4206e-119">その場合は、検索が成功した場合にのみ、参照戻り値を変更します。</span><span class="sxs-lookup"><span data-stu-id="4206e-119">In that case, you want to modify the reference return value only if the search is successful.</span></span>

<span data-ttu-id="4206e-120">次C#の例は、このシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="4206e-120">The following C# example illustrates this scenario.</span></span> <span data-ttu-id="4206e-121">定義、`Sentence`で記述されたクラスC#が含まれています、`FindNext`メソッドを指定した部分文字列で始まる文で次の単語を検索します。</span><span class="sxs-lookup"><span data-stu-id="4206e-121">It defines a `Sentence` class written in C# includes a `FindNext` method that finds the next word in a sentence that begins with a specified substring.</span></span> <span data-ttu-id="4206e-122">文字列は参照戻り値として返され、参照によりメソッドに渡される `Boolean` 変数は検索が成功したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4206e-122">The string is returned as a reference return value, and a `Boolean` variable passed by reference to the method indicates whether the search was successful.</span></span> <span data-ttu-id="4206e-123">参照戻り値、呼び出し元できましていないのみを読み取ることを返される値。そのユーザーも変更できますとで内部に含まれるデータにその変更が反映されます、`Sentence`クラス。</span><span class="sxs-lookup"><span data-stu-id="4206e-123">The reference return value indicates that the caller can not only read the returned value; he or she can also modify it, and that modification is reflected in the data contained internally in the `Sentence` class.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

<span data-ttu-id="4206e-124">参照を直接変更する戻り値の値ここでが信頼性が高く、ために、一致が見つかるし、文の最初の単語を返すメソッドの呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="4206e-124">Directly modifying the reference return value in this case is not reliable, since the method call may fail to find a match and return the first word in the sentence.</span></span> <span data-ttu-id="4206e-125">その場合は、呼び出し元は誤って文の最初の単語を変更します。</span><span class="sxs-lookup"><span data-stu-id="4206e-125">In that case, the caller will inadvertently modify the first word of the sentence.</span></span> <span data-ttu-id="4206e-126">返す、呼び出し元によってこれを回避できる可能性があります、 `null` (または`Nothing`Visual Basic で)。</span><span class="sxs-lookup"><span data-stu-id="4206e-126">This could be prevented by the caller returning a `null` (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="4206e-127">その場合は、値が文字列を変更しようとしていますが、`Nothing`スロー、<xref:System.NullReferenceException>します。</span><span class="sxs-lookup"><span data-stu-id="4206e-127">But in that case, attempting to modify a string whose value is `Nothing` throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="4206e-128">場合は、呼び出し元を返すことが防止することも<xref:System.String.Empty?displayProperty=nameWithType>、呼び出し元が値が文字列変数を定義する必要がありますが、<xref:System.String.Empty?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="4206e-128">If could also be prevented by the caller returning <xref:System.String.Empty?displayProperty=nameWithType>, but this requires that the caller define a string variable whose value is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4206e-129">変更後の文字列が格納されている文脈での単語にリレーションシップがあるないため、呼び出し元は、その文字列を変更できる、中に変更自体は目的、意味がありません、`Sentence`クラス。</span><span class="sxs-lookup"><span data-stu-id="4206e-129">While the caller can modify that string, the modification itself serves no purpose, since the modified string has no relationship to the words in the sentence stored by the `Sentence` class.</span></span>

<span data-ttu-id="4206e-130">このシナリオを処理する最善の方法では、参照戻り値を渡し、ヘルパー メソッドへの参照です。</span><span class="sxs-lookup"><span data-stu-id="4206e-130">The best way to handle this scenario is to pass the reference return value by reference to a helper method.</span></span> <span data-ttu-id="4206e-131">ヘルパー メソッドには、メソッド呼び出しが成功したし、変更する場合と、参照戻り値かどうかを判断するロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4206e-131">The helper method then contains the logic to determine whether the method call succeeded and, if it did, to modify the reference return value.</span></span> <span data-ttu-id="4206e-132">次の例では、考えられる実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="4206e-132">The following example provides a possible implementation.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a><span data-ttu-id="4206e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="4206e-133">See also</span></span>

- [<span data-ttu-id="4206e-134">値と参照渡しの引数を渡す</span><span class="sxs-lookup"><span data-stu-id="4206e-134">Passing arguments by value and by reference</span></span>](passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="4206e-135">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="4206e-135">Procedures in Visual Basic</span></span>](index.md)
