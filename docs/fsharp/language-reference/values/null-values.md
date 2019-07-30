---
title: null 値
description: F#プログラミング言語での null 値の使用方法について説明します。
ms.date: 03/22/2019
ms.openlocfilehash: 2038c0a461fec9884c51edd50c3c9f336104e30e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630807"
---
# <a name="null-values"></a><span data-ttu-id="253dd-103">null 値</span><span class="sxs-lookup"><span data-stu-id="253dd-103">Null Values</span></span>

<span data-ttu-id="253dd-104">このトピックでは、F# で null 値を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="253dd-104">This topic describes how the null value is used in F#.</span></span>

## <a name="null-value"></a><span data-ttu-id="253dd-105">Null 値</span><span class="sxs-lookup"><span data-stu-id="253dd-105">Null Value</span></span>

<span data-ttu-id="253dd-106">Null 値は通常使用されません F# での値または変数。</span><span class="sxs-lookup"><span data-stu-id="253dd-106">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="253dd-107">ただし、null は、特定の状況では異常な値として表示されます。</span><span class="sxs-lookup"><span data-stu-id="253dd-107">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="253dd-108">しない限り、null がない通常の値として許可 F# の型が定義されている場合、 [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f)属性型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="253dd-108">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="253dd-109">Null は使用可能な値型は、他の .NET 言語で定義されているが場合と、F# コードで null 値を発生可能性があるこのような型と相互運用するときにします。</span><span class="sxs-lookup"><span data-stu-id="253dd-109">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="253dd-110">F# で定義されているし、F# から厳密に使用される型、F# ライブラリを直接使用して null 値を作成する唯一の方法は使用する[Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977)または[Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)します。</span><span class="sxs-lookup"><span data-stu-id="253dd-110">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="253dd-111">ただし、F# 型の他の .NET 言語から使用されるまたは null 値が発生することがその型を使用して、F# など、.NET Framework で記述されていない API を使用している場合。</span><span class="sxs-lookup"><span data-stu-id="253dd-111">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="253dd-112">使用することができます、 `option` F# 参照変数を別の .NET 言語で使用できる null 値で使用するときに入力します。</span><span class="sxs-lookup"><span data-stu-id="253dd-112">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="253dd-113">オブジェクトがない場合は、 F# `option` null の代わりに型を使用`None`して、オプションの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="253dd-113">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="253dd-114">オブジェクトがある場合は`Some(obj)` 、オプションの`obj`値をオブジェクトと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="253dd-114">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="253dd-115">詳細については、[オプション](../options.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="253dd-115">For more information, see [Options](../options.md).</span></span> <span data-ttu-id="253dd-116">`null`では`Some x` 、で`x`ある場合に値をオプションにパックすることもできます。 `null`</span><span class="sxs-lookup"><span data-stu-id="253dd-116">Note that you can still pack a `null` value into an Option if, for `Some x`, `x` happens to be `null`.</span></span> <span data-ttu-id="253dd-117">このため、値が`None` `null`の場合はを使用することが重要です。</span><span class="sxs-lookup"><span data-stu-id="253dd-117">Because of this, it is important you use `None` when a value is `null`.</span></span>

<span data-ttu-id="253dd-118">`null`キーワードは、F# 言語では、有効なキーワードと、.NET Framework Api または他の .NET 言語で記述されている他の Api を使用しているときに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="253dd-118">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="253dd-119">Null 値が必要になる可能性がある2つの状況は、.NET API を呼び出し、引数として null 値を渡す場合と、.NET メソッド呼び出しからの戻り値または出力パラメーターを解釈する場合です。</span><span class="sxs-lookup"><span data-stu-id="253dd-119">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="253dd-120">.Net メソッドに null 値を渡すには、呼び出し元の`null`コードでキーワードを使用するだけです。</span><span class="sxs-lookup"><span data-stu-id="253dd-120">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="253dd-121">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="253dd-121">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="253dd-122">.NET メソッドから取得した null 値を解釈するには、可能であれば、パターンマッチングを使用します。</span><span class="sxs-lookup"><span data-stu-id="253dd-122">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="253dd-123">次のコード例は、パターン一致を使用して、入力ストリームの末尾を越え`ReadLine`て読み取ろうとしたときにから返される null 値を解釈する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="253dd-123">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="253dd-124">使用する場合など、他の方法で F# 型の null 値を生成することも`Array.zeroCreate`、呼び出す`Unchecked.defaultof`します。</span><span class="sxs-lookup"><span data-stu-id="253dd-124">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="253dd-125">Null 値をカプセル化するためには、このようなコードに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="253dd-125">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="253dd-126">専用の F# ライブラリでは、すべての関数で null 値をチェックする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="253dd-126">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="253dd-127">他の .net 言語との相互運用のためにライブラリを記述する場合は、または Visual Basic コードの`ArgumentNullException` C#場合と同様に、null 入力パラメーターのチェックを追加し、をスローすることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="253dd-127">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="253dd-128">次のコードを使用すると、任意の値が null かどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="253dd-128">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="253dd-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="253dd-129">See also</span></span>

- [<span data-ttu-id="253dd-130">値</span><span class="sxs-lookup"><span data-stu-id="253dd-130">Values</span></span>](index.md)
- [<span data-ttu-id="253dd-131">match 式</span><span class="sxs-lookup"><span data-stu-id="253dd-131">Match Expressions</span></span>](../match-expressions.md)
