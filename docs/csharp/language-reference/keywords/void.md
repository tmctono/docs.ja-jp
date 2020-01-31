---
title: void - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 0624b547ee2586334ac35d366ae3c8dfd14963ee
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742758"
---
# <a name="void-c-reference"></a><span data-ttu-id="c0e9c-102">void (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c0e9c-102">void (C# Reference)</span></span>

<span data-ttu-id="c0e9c-103">メソッドの戻り値の型として使用した場合、`void` はメソッドが値を返さないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0e9c-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="c0e9c-104">`void` は、メソッドのパラメーター リストに含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="c0e9c-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="c0e9c-105">パラメーターを取らず、値を返さないメソッドは、次のように宣言されます。</span><span class="sxs-lookup"><span data-stu-id="c0e9c-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="c0e9c-106">`void` は、不明な型へのポインターを宣言するために、unsafe コンテキストでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0e9c-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="c0e9c-107">詳しくは、「[ポインター型](../../programming-guide/unsafe-code-pointers/pointer-types.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c0e9c-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="c0e9c-108">`void` は、.NET Framework の <xref:System.Void?displayProperty=nameWithType> 型のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="c0e9c-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c0e9c-109">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="c0e9c-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c0e9c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0e9c-110">See also</span></span>

- [<span data-ttu-id="c0e9c-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="c0e9c-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c0e9c-112">C# キーワード</span><span class="sxs-lookup"><span data-stu-id="c0e9c-112">C# keywords</span></span>](index.md)
- [<span data-ttu-id="c0e9c-113">参照型</span><span class="sxs-lookup"><span data-stu-id="c0e9c-113">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="c0e9c-114">値型</span><span class="sxs-lookup"><span data-stu-id="c0e9c-114">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="c0e9c-115">メソッド</span><span class="sxs-lookup"><span data-stu-id="c0e9c-115">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="c0e9c-116">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="c0e9c-116">Unsafe code and pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
