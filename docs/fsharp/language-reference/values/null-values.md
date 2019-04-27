---
title: null 値
description: Null 値を使用する方法について説明します、F#プログラミング言語。
ms.date: 03/22/2019
ms.openlocfilehash: 93ac48eddf36981b9df550e76405c3175ae92e0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902279"
---
# <a name="null-values"></a><span data-ttu-id="b92d4-103">null 値</span><span class="sxs-lookup"><span data-stu-id="b92d4-103">Null Values</span></span>

<span data-ttu-id="b92d4-104">このトピックでは、F# で null 値を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b92d4-104">This topic describes how the null value is used in F#.</span></span>

## <a name="null-value"></a><span data-ttu-id="b92d4-105">Null 値</span><span class="sxs-lookup"><span data-stu-id="b92d4-105">Null Value</span></span>

<span data-ttu-id="b92d4-106">Null 値は通常使用されません F# での値または変数。</span><span class="sxs-lookup"><span data-stu-id="b92d4-106">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="b92d4-107">ただし、特定の状況で、外れ値として null が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b92d4-107">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="b92d4-108">しない限り、null がない通常の値として許可 F# の型が定義されている場合、 [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f)属性型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b92d4-108">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="b92d4-109">Null は使用可能な値型は、他の .NET 言語で定義されているが場合と、F# コードで null 値を発生可能性があるこのような型と相互運用するときにします。</span><span class="sxs-lookup"><span data-stu-id="b92d4-109">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="b92d4-110">F# で定義されているし、F# から厳密に使用される型、F# ライブラリを直接使用して null 値を作成する唯一の方法は使用する[Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977)または[Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)します。</span><span class="sxs-lookup"><span data-stu-id="b92d4-110">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="b92d4-111">ただし、F# 型の他の .NET 言語から使用されるまたは null 値が発生することがその型を使用して、F# など、.NET Framework で記述されていない API を使用している場合。</span><span class="sxs-lookup"><span data-stu-id="b92d4-111">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="b92d4-112">使用することができます、 `option` F# 参照変数を別の .NET 言語で使用できる null 値で使用するときに入力します。</span><span class="sxs-lookup"><span data-stu-id="b92d4-112">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="b92d4-113">Null の場合、代わりに、 F# `option`型、オプションの値を使用する`None`オブジェクトが存在しない場合。</span><span class="sxs-lookup"><span data-stu-id="b92d4-113">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="b92d4-114">オプションの値を使用する`Some(obj)`オブジェクト`obj`オブジェクトがある場合。</span><span class="sxs-lookup"><span data-stu-id="b92d4-114">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="b92d4-115">詳細については、[オプション](../options.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92d4-115">For more information, see [Options](../options.md).</span></span> <span data-ttu-id="b92d4-116">まだをパックすることに注意してください、`null`オプションに値の場合の`Some x`、`x`たまたま`null`。</span><span class="sxs-lookup"><span data-stu-id="b92d4-116">Note that you can still pack a `null` value into an Option if, for `Some x`, `x` happens to be `null`.</span></span> <span data-ttu-id="b92d4-117">このためが使用する重要な`None`、値が`null`します。</span><span class="sxs-lookup"><span data-stu-id="b92d4-117">Because of this, it is important you use `None` when a value is `null`.</span></span>

<span data-ttu-id="b92d4-118">`null`キーワードは、F# 言語では、有効なキーワードと、.NET Framework Api または他の .NET 言語で記述されている他の Api を使用しているときに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b92d4-118">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="b92d4-119">Null 値をする必要があります、2 つの状況は、.NET API を呼び出すし、引数として null 値を渡すされ、戻り値または .NET メソッドの呼び出しからの出力パラメーターを解釈するときに。</span><span class="sxs-lookup"><span data-stu-id="b92d4-119">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="b92d4-120">.NET メソッドに null 値を渡すだけ使用して、`null`呼び出しコードのキーワード。</span><span class="sxs-lookup"><span data-stu-id="b92d4-120">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="b92d4-121">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="b92d4-121">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="b92d4-122">.NET メソッドから取得した null 値を解釈するには、可能な場合に一致するパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="b92d4-122">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="b92d4-123">次のコード例は、パターン マッチングを使用して、返される null 値を解釈する方法を示しています。`ReadLine`入力ストリームの末尾を越えて読み取りを実行しようとする場合。</span><span class="sxs-lookup"><span data-stu-id="b92d4-123">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="b92d4-124">使用する場合など、他の方法で F# 型の null 値を生成することも`Array.zeroCreate`、呼び出す`Unchecked.defaultof`します。</span><span class="sxs-lookup"><span data-stu-id="b92d4-124">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="b92d4-125">このようなコードをカプセル化された null 値を保持するには注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="b92d4-125">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="b92d4-126">専用の F# ライブラリでは、すべての関数で null 値をチェックする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b92d4-126">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="b92d4-127">他の .NET 言語と相互運用ライブラリを作成する場合 null チェックが入力パラメーターと、スローを追加する必要があります、 `ArgumentNullException`、c# または Visual Basic コードで行うのと同様です。</span><span class="sxs-lookup"><span data-stu-id="b92d4-127">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="b92d4-128">次のコードを使用すると、任意の値が null を確認します。</span><span class="sxs-lookup"><span data-stu-id="b92d4-128">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="b92d4-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b92d4-129">See also</span></span>

- [<span data-ttu-id="b92d4-130">値</span><span class="sxs-lookup"><span data-stu-id="b92d4-130">Values</span></span>](index.md)
- [<span data-ttu-id="b92d4-131">match 式</span><span class="sxs-lookup"><span data-stu-id="b92d4-131">Match Expressions</span></span>](../match-expressions.md)
