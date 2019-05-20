---
title: '方法: ポインターを使用して配列要素にアクセスする - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: b1538068f3ba37a7637e7dc3913e9511d4380daf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635181"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="08c93-102">方法: ポインターを使用して配列要素にアクセスする (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="08c93-102">How to: access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="08c93-103">安全ではないコンテキストでは、次の例のように、ポインターを利用してメモリ内の要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="08c93-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="08c93-104">角かっこ内の式は `int`、`uint`、`long`、`ulong` に暗黙的に変換できるものでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="08c93-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="08c93-105">演算 `p[e]` は `*(p+e)` と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="08c93-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="08c93-106">C や C++ と同様に、ポインターで要素にアクセスする行為では、範囲外のエラーがチェックされません。</span><span class="sxs-lookup"><span data-stu-id="08c93-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="08c93-107">例</span><span class="sxs-lookup"><span data-stu-id="08c93-107">Example</span></span>

<span data-ttu-id="08c93-108">この例では、123 のメモリ場所が文字配列 `charPointer` に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="08c93-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="08c93-109">この配列を利用し、2 つの [for](../../../csharp/language-reference/keywords/for.md) ループの小文字と大文字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="08c93-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="08c93-110">式 `charPointer[i]` は式 `*(charPointer + i)` と等しく、2 つの式のいずれを利用しても同じ結果が得られることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="08c93-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

 [!code-csharp[csProgGuidePointers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#11)]

 [!code-csharp[csProgGuidePointers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#12)]

<span data-ttu-id="08c93-111">**大文字:**</span><span class="sxs-lookup"><span data-stu-id="08c93-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="08c93-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="08c93-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="08c93-113">**小文字:**</span><span class="sxs-lookup"><span data-stu-id="08c93-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="08c93-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="08c93-114">**abcdefghijklmnopqrstuvwxyz**</span></span>  

## <a name="see-also"></a><span data-ttu-id="08c93-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="08c93-115">See also</span></span>

- [<span data-ttu-id="08c93-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="08c93-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="08c93-117">型</span><span class="sxs-lookup"><span data-stu-id="08c93-117">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="08c93-118">unsafe</span><span class="sxs-lookup"><span data-stu-id="08c93-118">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="08c93-119">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="08c93-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="08c93-120">stackalloc</span><span class="sxs-lookup"><span data-stu-id="08c93-120">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
