---
title: '方法: null 許容値型を識別する - C# プログラミング ガイド'
ms.custom: seodec18
description: 型が null 許容値型か、またはインスタンスが null 許容値型かどうかを判断する方法について学習します。
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: 15b1ffedf57648955ee5a004514841a5d140292b
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392611"
---
# <a name="how-to-identify-a-nullable-value-type-c-programming-guide"></a><span data-ttu-id="e3583-103">方法: null 許容値型を識別する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e3583-103">How to: identify a nullable value type (C# Programming Guide)</span></span>

<span data-ttu-id="e3583-104">次の例は、<xref:System.Type?displayProperty=nameWithType> インスタンスがクローズ ジェネリック null 許容値型 (つまり、指定された型パラメーター `T` を使用する <xref:System.Nullable%601?displayProperty=nameWithType> 型) を表すかどうかを判断する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e3583-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a closed generic nullable value type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="e3583-105">例で示されているとおり、<xref:System.Type?displayProperty=nameWithType> オブジェクトの作成には、[typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3583-105">As the example shows, you use the [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="e3583-106">インスタンスが null 許容値型かどうかを判断したい場合は、<xref:System.Type> インスタンスが前述のコードでテストされるように、<xref:System.Object.GetType%2A?displayProperty=nameWithType> メソッドは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="e3583-106">If you want to determine whether an instance is of a nullable value type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="e3583-107">null 許容値型のインスタンスで <xref:System.Object.GetType%2A?displayProperty=nameWithType> メソッドを呼び出した場合、そのインスタンスは <xref:System.Object> に[ボクシング](using-nullable-types.md#boxing-and-unboxing)されます。</span><span class="sxs-lookup"><span data-stu-id="e3583-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable value type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="e3583-108">null 許容値型の null 以外のインスタンスのボクシングは、基になる型の値のボクシングと等しいので、<xref:System.Object.GetType%2A> は、null 許容値型の基になる型を表す <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e3583-108">As boxing of a non-null instance of a nullable value type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable value type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="e3583-109">インスタンスが null 許容値型であるかどうかの判断には、[is](../../language-reference/keywords/is.md) 演算子は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="e3583-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable value type.</span></span> <span data-ttu-id="e3583-110">次の例のとおり、`is` 演算子の使用では、null 許容値型のインスタンスの型とその基になる型は判別できません。</span><span class="sxs-lookup"><span data-stu-id="e3583-110">As the following example shows, you cannot distinguish types of instances of a nullable value type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="e3583-111">次の例のコードを使用すると、インスタンスが null 許容値型であるかどうかを判別することができます。</span><span class="sxs-lookup"><span data-stu-id="e3583-111">You can use the code presented in the following example to determine whether an instance is of a nullable value type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]

## <a name="see-also"></a><span data-ttu-id="e3583-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3583-112">See also</span></span>

- [<span data-ttu-id="e3583-113">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="e3583-113">Nullable value types</span></span>](index.md)
- [<span data-ttu-id="e3583-114">null 許容値型の使用</span><span class="sxs-lookup"><span data-stu-id="e3583-114">Using nullable value types</span></span>](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
