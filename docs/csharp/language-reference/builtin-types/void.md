---
title: void - C# リファレンス
ms.date: 02/11/2020
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: c6c1c28e3d7a53a1dcadcf50d8d7f42c8c8aeee4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846211"
---
# <a name="void-c-reference"></a><span data-ttu-id="e919e-102">void (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e919e-102">void (C# reference)</span></span>

<span data-ttu-id="e919e-103">`void`メソッド[ (または ](../../programming-guide/classes-and-structs/methods.md)ローカル関数[) が値を返さないことを指定するには、メソッドの戻り値の型として ](../../programming-guide/classes-and-structs/local-functions.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e919e-103">You use `void` as the return type of a [method](../../programming-guide/classes-and-structs/methods.md) (or a [local function](../../programming-guide/classes-and-structs/local-functions.md)) to specify that the method doesn't return a value.</span></span>

[!code-csharp[void method](snippets/VoidType.cs#VoidExample)]

<span data-ttu-id="e919e-104">さらに、不明な型へのポインターを宣言するための参照型として `void` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e919e-104">You can also use `void` as a referent type to declare a pointer to an unknown type.</span></span> <span data-ttu-id="e919e-105">詳しくは、「[ポインター型](../../programming-guide/unsafe-code-pointers/pointer-types.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e919e-105">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="e919e-106">変数の型として `void` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e919e-106">You cannot use `void` as the type of a variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="e919e-107">参照</span><span class="sxs-lookup"><span data-stu-id="e919e-107">See also</span></span>

- [<span data-ttu-id="e919e-108">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="e919e-108">C# reference</span></span>](../index.md)
- <xref:System.Void?displayProperty=nameWithType>
