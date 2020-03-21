---
title: 参照戻り値
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: f2a92c584dbb12a322e28435d797fa4d7c2f6dbb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186933"
---
# <a name="support-for-reference-return-values-visual-basic"></a><span data-ttu-id="61f9c-102">参照の戻り値のサポート</span><span class="sxs-lookup"><span data-stu-id="61f9c-102">Support for reference return values (Visual Basic)</span></span>

<span data-ttu-id="61f9c-103">C# 7.0 以降、C# 言語では*参照戻り値*がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="61f9c-103">Starting with C# 7.0, the C# language supports *reference return values*.</span></span> <span data-ttu-id="61f9c-104">参照の戻り値を理解する 1 つの方法は、参照によってメソッドに渡される引数とは逆であるということです。</span><span class="sxs-lookup"><span data-stu-id="61f9c-104">One way to understand reference return values is that they are the opposite of arguments that are passed by reference to a method.</span></span> <span data-ttu-id="61f9c-105">参照によって渡された引数が変更されると、その変更は呼び出し元の変数の値に反映されます。</span><span class="sxs-lookup"><span data-stu-id="61f9c-105">When an argument passed by reference is modified, the changes are reflected in value of the variable on the caller.</span></span> <span data-ttu-id="61f9c-106">メソッドが呼び出し元に参照戻り値を提供すると、呼び出し元が参照戻り値に加えた変更が呼び出されたメソッドのデータに反映されます。</span><span class="sxs-lookup"><span data-stu-id="61f9c-106">When an method provides a reference return value to a caller, modifications made to the reference return value by the caller are reflected in the called method's data.</span></span>

<span data-ttu-id="61f9c-107">Visual Basic では、参照戻り値を使用してメソッドを作成することはできませんが、参照の戻り値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="61f9c-107">Visual Basic does not allow you to author methods with reference return values, but it does allow you to consume reference return values.</span></span> <span data-ttu-id="61f9c-108">つまり、参照の戻り値を持つメソッドを呼び出して、その戻り値を変更すると、参照の戻り値への変更が呼び出されたメソッドのデータに反映されます。</span><span class="sxs-lookup"><span data-stu-id="61f9c-108">In other words, you can call a method with a reference return value and modify that return value, and changes to the reference return value are reflected in the called method's data.</span></span>

## <a name="modifying-the-ref-return-value-directly"></a><span data-ttu-id="61f9c-109">ref 戻り値を直接変更する</span><span class="sxs-lookup"><span data-stu-id="61f9c-109">Modifying the ref return value directly</span></span>

<span data-ttu-id="61f9c-110">常に成功し、パラメーターを持`ByRef`たないメソッドの場合は、参照の戻り値を直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="61f9c-110">For methods that always succeed and have no `ByRef` parameters, you can modify the reference return value directly.</span></span> <span data-ttu-id="61f9c-111">これは、参照の戻り値を返す式に新しい値を代入することによって行います。</span><span class="sxs-lookup"><span data-stu-id="61f9c-111">You do this by assigning the new value to the expressions that returns the reference return value.</span></span>

<span data-ttu-id="61f9c-112">次の C# の`NumericValue.IncrementValue`例では、内部値をインクリメントし、それを参照戻り値として返すメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="61f9c-112">The following C# example defines a `NumericValue.IncrementValue` method that increments an internal value and returns it as a reference return value.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

<span data-ttu-id="61f9c-113">次の Visual Basic の例では、参照の戻り値が呼び出し元によって変更されます。</span><span class="sxs-lookup"><span data-stu-id="61f9c-113">The reference return value is then modified by the caller in the following Visual Basic example.</span></span> <span data-ttu-id="61f9c-114">メソッド呼び出しを`NumericValue.IncrementValue`行う行では、メソッドに値が割り当てられていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="61f9c-114">Note that the line with the `NumericValue.IncrementValue` method call does not assign a value to the method.</span></span> <span data-ttu-id="61f9c-115">代わりに、メソッドによって返される参照戻り値に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="61f9c-115">Instead, it assigns a value to the reference return value returned by the method.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a><span data-ttu-id="61f9c-116">ヘルパー メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="61f9c-116">Using a helper method</span></span>

<span data-ttu-id="61f9c-117">また、メソッド呼び出しの参照戻り値を直接変更する場合も、必ずしも望ましいとは限りません。</span><span class="sxs-lookup"><span data-stu-id="61f9c-117">In other cases, modifying the reference return value of a method call directly may not always be desirable.</span></span> <span data-ttu-id="61f9c-118">たとえば、文字列を返す検索メソッドは、必ずしも一致するものを見つけるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="61f9c-118">For example, a search method that returns a string may not always find a match.</span></span> <span data-ttu-id="61f9c-119">その場合、検索が成功した場合にのみ参照戻り値を変更します。</span><span class="sxs-lookup"><span data-stu-id="61f9c-119">In that case, you want to modify the reference return value only if the search is successful.</span></span>

<span data-ttu-id="61f9c-120">次の C# の例は、このシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="61f9c-120">The following C# example illustrates this scenario.</span></span> <span data-ttu-id="61f9c-121">C#`Sentence`で記述されたクラスには、`FindNext`指定された部分文字列で始まる文の次の単語を検索するメソッドが含まれていることを定義します。</span><span class="sxs-lookup"><span data-stu-id="61f9c-121">It defines a `Sentence` class written in C# includes a `FindNext` method that finds the next word in a sentence that begins with a specified substring.</span></span> <span data-ttu-id="61f9c-122">文字列は参照戻り値として返され、参照によりメソッドに渡される `Boolean` 変数は検索が成功したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="61f9c-122">The string is returned as a reference return value, and a `Boolean` variable passed by reference to the method indicates whether the search was successful.</span></span> <span data-ttu-id="61f9c-123">参照の戻り値は、戻り値の読み取りに加えて、呼び出し元が値を変更できること、およびクラスに内部に`Sentence`含まれるデータに変更が反映されることを示します。</span><span class="sxs-lookup"><span data-stu-id="61f9c-123">The reference return value indicates that in addition to reading the returned value, the caller can also modify it, and that modification is reflected in the data contained internally in the `Sentence` class.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

<span data-ttu-id="61f9c-124">この場合、参照戻り値を直接変更することは、メソッド呼び出しが一致するものを見つけて文の最初の単語を返すことができない可能性があるため、信頼できません。</span><span class="sxs-lookup"><span data-stu-id="61f9c-124">Directly modifying the reference return value in this case is not reliable, since the method call may fail to find a match and return the first word in the sentence.</span></span> <span data-ttu-id="61f9c-125">その場合、呼び出し元は誤って文の最初の単語を変更します。</span><span class="sxs-lookup"><span data-stu-id="61f9c-125">In that case, the caller will inadvertently modify the first word of the sentence.</span></span> <span data-ttu-id="61f9c-126">これは、呼び出し元が`null`(または`Nothing`Visual Basic で) を返すことによって防止できます。</span><span class="sxs-lookup"><span data-stu-id="61f9c-126">This could be prevented by the caller returning a `null` (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="61f9c-127">しかし、その場合、値がスローされる`Nothing`文字列を変更しようとすると、 <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="61f9c-127">But in that case, attempting to modify a string whose value is `Nothing` throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="61f9c-128">呼び出し元が を返<xref:System.String.Empty?displayProperty=nameWithType>しても防ぐことが可能ですが、この場合は、呼び出<xref:System.String.Empty?displayProperty=nameWithType>し元が値を持つ文字列変数を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61f9c-128">If could also be prevented by the caller returning <xref:System.String.Empty?displayProperty=nameWithType>, but this requires that the caller define a string variable whose value is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span> <span data-ttu-id="61f9c-129">呼び出し元はその文字列を変更できますが、変更された文字列はクラスによって格納されている文の単語と関係がないため、変更自体は目的を`Sentence`果たしません。</span><span class="sxs-lookup"><span data-stu-id="61f9c-129">While the caller can modify that string, the modification itself serves no purpose, since the modified string has no relationship to the words in the sentence stored by the `Sentence` class.</span></span>

<span data-ttu-id="61f9c-130">このシナリオを処理する最善の方法は、参照によって参照の戻り値をヘルパー メソッドに渡す方法です。</span><span class="sxs-lookup"><span data-stu-id="61f9c-130">The best way to handle this scenario is to pass the reference return value by reference to a helper method.</span></span> <span data-ttu-id="61f9c-131">ヘルパー メソッドには、メソッド呼び出しが成功したかどうかを判断するロジックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="61f9c-131">The helper method then contains the logic to determine whether the method call succeeded and, if it did, to modify the reference return value.</span></span> <span data-ttu-id="61f9c-132">次の例では、実装可能な実装を示します。</span><span class="sxs-lookup"><span data-stu-id="61f9c-132">The following example provides a possible implementation.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a><span data-ttu-id="61f9c-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="61f9c-133">See also</span></span>

- [<span data-ttu-id="61f9c-134">値と参照による引数の受け渡し</span><span class="sxs-lookup"><span data-stu-id="61f9c-134">Passing arguments by value and by reference</span></span>](passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="61f9c-135">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="61f9c-135">Procedures in Visual Basic</span></span>](index.md)
