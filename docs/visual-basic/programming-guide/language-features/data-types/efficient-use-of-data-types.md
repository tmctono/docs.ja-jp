---
title: データ型の有効な使用方法 (Visual Basic)
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
ms.openlocfilehash: f85acfe7592d7b90423107e0d45bb007fce5f4a8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64601156"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="996f9-102">データ型の有効な使用方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="996f9-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="996f9-103">宣言されていない変数とデータ型なしで宣言された変数が割り当てられている、`Object`データ型。</span><span class="sxs-lookup"><span data-stu-id="996f9-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="996f9-104">プログラムを迅速に記述が簡単になります。 ただし、ことより緩やかに変化を実行することがあります。</span><span class="sxs-lookup"><span data-stu-id="996f9-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="996f9-105">厳密な型指定</span><span class="sxs-lookup"><span data-stu-id="996f9-105">Strong Typing</span></span>  
 <span data-ttu-id="996f9-106">すべての変数のデータ型の指定と呼びます*厳密な型指定*します。</span><span class="sxs-lookup"><span data-stu-id="996f9-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="996f9-107">厳密な型指定を使用して、いくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="996f9-107">Using strong typing has several advantages:</span></span>  
  
- <span data-ttu-id="996f9-108">変数に IntelliSense をサポートをできます。</span><span class="sxs-lookup"><span data-stu-id="996f9-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="996f9-109">これにより、コードに入力すると、プロパティやその他のメンバーを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="996f9-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
- <span data-ttu-id="996f9-110">コンパイラの型チェックの利点がかかります。</span><span class="sxs-lookup"><span data-stu-id="996f9-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="996f9-111">これは、オーバーフローなどのエラーにより実行時に失敗するステートメントをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="996f9-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="996f9-112">サポートしていないオブジェクトに対するメソッドの呼び出しをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="996f9-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
- <span data-ttu-id="996f9-113">コードの実行速度が速くなります。</span><span class="sxs-lookup"><span data-stu-id="996f9-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="996f9-114">最も効率的なデータ型</span><span class="sxs-lookup"><span data-stu-id="996f9-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="996f9-115">決して分数を含む変数、整数データ型は非整数の型よりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="996f9-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="996f9-116">Visual basic で`Integer`と`UInteger`は最も効率的な数値型。</span><span class="sxs-lookup"><span data-stu-id="996f9-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="996f9-117">数値の小数部から成る場合`Double`を最も効率的なデータ型は、現在のプラットフォーム上のプロセッサでは、倍精度浮動小数点演算を実行するためです。</span><span class="sxs-lookup"><span data-stu-id="996f9-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="996f9-118">ただし、操作を`Double`などの整数型と同様に高速でない`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="996f9-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="996f9-119">データ型の指定</span><span class="sxs-lookup"><span data-stu-id="996f9-119">Specifying Data Type</span></span>  
 <span data-ttu-id="996f9-120">使用して、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)特定の型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="996f9-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="996f9-121">使用して、アクセス レベルを指定することが同時に、[Public](../../../../visual-basic/language-reference/modifiers/public.md)、 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)、[Friend](../../../../visual-basic/language-reference/modifiers/friend.md)、または[Private](../../../../visual-basic/language-reference/modifiers/private.md)に示すように、キーワード、次の例です。</span><span class="sxs-lookup"><span data-stu-id="996f9-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="996f9-122">文字の変換</span><span class="sxs-lookup"><span data-stu-id="996f9-122">Character Conversion</span></span>  
 <span data-ttu-id="996f9-123">`AscW`と`ChrW`関数は Unicode で動作します。</span><span class="sxs-lookup"><span data-stu-id="996f9-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="996f9-124">優先的に使用する必要があります`Asc`と`Chr`Unicode との間に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="996f9-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="996f9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="996f9-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="996f9-126">データの種類</span><span class="sxs-lookup"><span data-stu-id="996f9-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="996f9-127">数値のデータ型</span><span class="sxs-lookup"><span data-stu-id="996f9-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="996f9-128">変数宣言</span><span class="sxs-lookup"><span data-stu-id="996f9-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="996f9-129">IntelliSense の使用</span><span class="sxs-lookup"><span data-stu-id="996f9-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
