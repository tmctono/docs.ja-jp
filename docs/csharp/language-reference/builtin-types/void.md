---
title: void - C# リファレンス
ms.date: 02/11/2020
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: f7ca3f83bc1980a16e45f22bbfd51e6861b0e5e7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453776"
---
# <a name="void-c-reference"></a><span data-ttu-id="fe293-102">void (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="fe293-102">void (C# reference)</span></span>

<span data-ttu-id="fe293-103">[メソッド](../../programming-guide/classes-and-structs/methods.md) (または [ローカル関数](../../programming-guide/classes-and-structs/local-functions.md)) が値を返さないことを指定するには、メソッドの戻り値の型として `void` を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe293-103">You use `void` as the return type of a [method](../../programming-guide/classes-and-structs/methods.md) (or a [local function](../../programming-guide/classes-and-structs/local-functions.md)) to specify that the method doesn't return a value.</span></span>

[!code-csharp[void method](~/samples/csharp/language-reference/builtin-types/VoidType.cs#VoidExample)]

<span data-ttu-id="fe293-104">さらに、不明な型へのポインターを宣言するための参照型として `void` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe293-104">You can also use `void` as a referent type to declare a pointer to an unknown type.</span></span> <span data-ttu-id="fe293-105">詳しくは、「[ポインター型](../../programming-guide/unsafe-code-pointers/pointer-types.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe293-105">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="fe293-106">変数の型として `void` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fe293-106">You cannot use `void` as the type of a variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe293-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe293-107">See also</span></span>

- [<span data-ttu-id="fe293-108">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="fe293-108">C# reference</span></span>](../index.md)
- <xref:System.Void?displayProperty=nameWithType>
