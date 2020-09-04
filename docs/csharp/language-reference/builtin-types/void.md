---
description: C# での void キーワードについて
title: void - C# リファレンス
ms.date: 02/11/2020
f1_keywords:
- void_CSharpKeyword
- void
- (void)
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: c0282a1eafd03506cd9ff05b209b2a27af216b2f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118157"
---
# <a name="void-c-reference"></a><span data-ttu-id="987ea-103">void (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="987ea-103">void (C# reference)</span></span>

<span data-ttu-id="987ea-104">[メソッド](../../programming-guide/classes-and-structs/methods.md) (または [ローカル関数](../../programming-guide/classes-and-structs/local-functions.md)) が値を返さないことを指定するには、メソッドの戻り値の型として `void` を使用します。</span><span class="sxs-lookup"><span data-stu-id="987ea-104">You use `void` as the return type of a [method](../../programming-guide/classes-and-structs/methods.md) (or a [local function](../../programming-guide/classes-and-structs/local-functions.md)) to specify that the method doesn't return a value.</span></span>

[!code-csharp[void method](snippets/VoidType.cs#VoidExample)]

<span data-ttu-id="987ea-105">さらに、不明な型へのポインターを宣言するための参照型として `void` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="987ea-105">You can also use `void` as a referent type to declare a pointer to an unknown type.</span></span> <span data-ttu-id="987ea-106">詳しくは、「[ポインター型](../../programming-guide/unsafe-code-pointers/pointer-types.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="987ea-106">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="987ea-107">変数の型として `void` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="987ea-107">You cannot use `void` as the type of a variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="987ea-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="987ea-108">See also</span></span>

- [<span data-ttu-id="987ea-109">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="987ea-109">C# reference</span></span>](../index.md)
- <xref:System.Void?displayProperty=nameWithType>
