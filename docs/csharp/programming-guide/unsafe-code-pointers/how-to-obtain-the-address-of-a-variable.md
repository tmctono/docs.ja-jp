---
title: '方法: 変数のアドレスを取得する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
ms.openlocfilehash: bc5776bc57096b88a71ff786915553ae9aa04b7b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635059"
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="e1fb0-102">方法: 変数のアドレスを取得する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e1fb0-102">How to: obtain the address of a variable (C# Programming Guide)</span></span>

<span data-ttu-id="e1fb0-103">固定変数に評価される単項式のアドレスを取得するには、address-of 演算子 `&` を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator `&`:</span></span>  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="e1fb0-104">address-of 演算子は、変数にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="e1fb0-105">変数が移動可能な変数である場合、[fixed ステートメント](../../../csharp/language-reference/keywords/fixed-statement.md)を使用して変数のアドレスを取得する前に、一時的に変数を固定できます。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span> <span data-ttu-id="e1fb0-106">移動可能変数の詳細については、「[固定と移動可能変数](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-106">For more information about moveable variables, see [Fixed and moveable variables](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables).</span></span> 
  
 <span data-ttu-id="e1fb0-107">ユーザーは変数が初期化されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-107">It's your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="e1fb0-108">変数が初期化されていない場合、コンパイラはエラー メッセージを発行しません。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-108">The compiler doesn't issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="e1fb0-109">定数または値のアドレスを取得できません。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-109">You can't get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1fb0-110">例</span><span class="sxs-lookup"><span data-stu-id="e1fb0-110">Example</span></span>  
 <span data-ttu-id="e1fb0-111">この例では、`int`、`p` へのポインターを宣言し、整数変数 `number` のアドレスを代入します。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-111">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="e1fb0-112">変数 `number` は `*p` への代入の結果として初期化されます。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-112">The variable `number` is initialized as a result of the assignment to `*p`.</span></span> <span data-ttu-id="e1fb0-113">この代入ステートメントをコメント アウトする場合は、変数 `number` の初期化が削除されますが、コンパイル時のエラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-113">If you comment out this assignment statement, the initialization of the variable `number` is removed, but no compile-time error is issued.</span></span>  

> [!NOTE]
> <span data-ttu-id="e1fb0-114">[`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) コンパイラ オプションを指定してこの例をコンパイルしてください。</span><span class="sxs-lookup"><span data-stu-id="e1fb0-114">Compile this example with the [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="e1fb0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1fb0-115">See also</span></span>

- [<span data-ttu-id="e1fb0-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e1fb0-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e1fb0-117">ポインター型</span><span class="sxs-lookup"><span data-stu-id="e1fb0-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="e1fb0-118">型</span><span class="sxs-lookup"><span data-stu-id="e1fb0-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="e1fb0-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="e1fb0-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="e1fb0-120">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="e1fb0-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="e1fb0-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="e1fb0-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
