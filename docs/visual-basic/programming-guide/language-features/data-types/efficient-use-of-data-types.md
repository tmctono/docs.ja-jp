---
title: データ型の有効な使用方法
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 621dec7537e9c993024e271b96ab8706baf89885
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350106"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="840df-102">データ型の有効な使用方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="840df-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="840df-103">宣言されていない変数およびデータ型を使用せずに宣言された変数には、`Object` データ型が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="840df-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="840df-104">これにより、プログラムをすばやく簡単に記述できるようになりますが、実行速度が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="840df-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>

## <a name="strong-typing"></a><span data-ttu-id="840df-105">厳密な型指定</span><span class="sxs-lookup"><span data-stu-id="840df-105">Strong Typing</span></span>
 <span data-ttu-id="840df-106">すべての変数のデータ型を指定することを、*厳密な*型指定と呼びます。</span><span class="sxs-lookup"><span data-stu-id="840df-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="840df-107">厳密な型指定を使用すると、いくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="840df-107">Using strong typing has several advantages:</span></span>

- <span data-ttu-id="840df-108">これにより、変数の IntelliSense サポートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="840df-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="840df-109">これにより、コードで入力するときに、プロパティや他のメンバーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="840df-109">This allows you to see their properties and other members as you type in the code.</span></span>

- <span data-ttu-id="840df-110">コンパイラの型チェックを利用します。</span><span class="sxs-lookup"><span data-stu-id="840df-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="840df-111">これは、オーバーフローなどのエラーによって実行時に失敗する可能性があるステートメントをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="840df-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="840df-112">また、サポートされていないオブジェクトのメソッドの呼び出しもキャッチします。</span><span class="sxs-lookup"><span data-stu-id="840df-112">It also catches calls to methods on objects that do not support them.</span></span>

- <span data-ttu-id="840df-113">これにより、コードの実行時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="840df-113">It results in faster execution of your code.</span></span>

## <a name="most-efficient-data-types"></a><span data-ttu-id="840df-114">最も効率的なデータ型</span><span class="sxs-lookup"><span data-stu-id="840df-114">Most Efficient Data Types</span></span>
 <span data-ttu-id="840df-115">分数を含まない変数の場合、整数データ型は非整数型よりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="840df-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="840df-116">Visual Basic では、`Integer` と `UInteger` が最も効率的な数値型です。</span><span class="sxs-lookup"><span data-stu-id="840df-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>

 <span data-ttu-id="840df-117">小数値の場合、現在のプラットフォームのプロセッサは倍精度で浮動小数点演算を実行するため、`Double` は最も効率的なデータ型です。</span><span class="sxs-lookup"><span data-stu-id="840df-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="840df-118">ただし、`Double` の操作は、`Integer`などの整数型ほど高速ではありません。</span><span class="sxs-lookup"><span data-stu-id="840df-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>

## <a name="specifying-data-type"></a><span data-ttu-id="840df-119">データ型の指定</span><span class="sxs-lookup"><span data-stu-id="840df-119">Specifying Data Type</span></span>
 <span data-ttu-id="840df-120">[Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を使用して、特定の型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="840df-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="840df-121">次の例に示すように、 [Public](../../../../visual-basic/language-reference/modifiers/public.md)、 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)、 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)、または[Private](../../../../visual-basic/language-reference/modifiers/private.md)キーワードを使用して、アクセスレベルを同時に指定できます。</span><span class="sxs-lookup"><span data-stu-id="840df-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a><span data-ttu-id="840df-122">文字変換</span><span class="sxs-lookup"><span data-stu-id="840df-122">Character Conversion</span></span>
 <span data-ttu-id="840df-123">`AscW` 関数と `ChrW` 関数は Unicode で動作します。</span><span class="sxs-lookup"><span data-stu-id="840df-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="840df-124">これらの設定は、`Asc` と `Chr`に使用する必要があります。これは、Unicode との間で変換を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="840df-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>

## <a name="see-also"></a><span data-ttu-id="840df-125">参照</span><span class="sxs-lookup"><span data-stu-id="840df-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="840df-126">データの種類</span><span class="sxs-lookup"><span data-stu-id="840df-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="840df-127">数値のデータ型</span><span class="sxs-lookup"><span data-stu-id="840df-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="840df-128">変数宣言</span><span class="sxs-lookup"><span data-stu-id="840df-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="840df-129">IntelliSense の使用</span><span class="sxs-lookup"><span data-stu-id="840df-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
