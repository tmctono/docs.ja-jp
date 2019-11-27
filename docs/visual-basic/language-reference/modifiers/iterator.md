---
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 9d7eaf186bae544031487ce027505e1e0d4ae0f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351524"
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="c429f-102">反復子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c429f-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="c429f-103">関数または `Get` アクセサーが反復子であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="c429f-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c429f-104">コメント</span><span class="sxs-lookup"><span data-stu-id="c429f-104">Remarks</span></span>  
 <span data-ttu-id="c429f-105">*反復子*は、コレクションに対してカスタムの反復処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="c429f-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="c429f-106">反復子は、 [Yield](../../../visual-basic/language-reference/statements/yield-statement.md)ステートメントを使用して、コレクション内の各要素を1回に1つ返します。</span><span class="sxs-lookup"><span data-stu-id="c429f-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="c429f-107">`Yield` ステートメントに到達すると、コード内の現在の場所が保持されます。</span><span class="sxs-lookup"><span data-stu-id="c429f-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="c429f-108">次回、反復子メソッドが呼び出されると、この位置から実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="c429f-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="c429f-109">反復子は、関数として実装することも、プロパティ定義の `Get` アクセサーとして実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="c429f-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="c429f-110">`Iterator` 修飾子は、iterator 関数または `Get` アクセサーの宣言に記述されます。</span><span class="sxs-lookup"><span data-stu-id="c429f-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="c429f-111">For Each を使用して、クライアントコードから反復子を呼び出します。 [次のステートメント](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c429f-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="c429f-112">反復子関数または `Get` アクセサーの戻り値の型は、<xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator>、または <xref:System.Collections.Generic.IEnumerator%601>にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c429f-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="c429f-113">反復子に `ByRef` パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="c429f-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="c429f-114">反復子を、イベント、インスタンス コンストラクター、静的コンストラクター、静的デストラクターで指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c429f-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="c429f-115">反復子は、匿名関数にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c429f-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="c429f-116">詳細については、「[反復子](../../programming-guide/concepts/iterators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c429f-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="c429f-117">使用方法</span><span class="sxs-lookup"><span data-stu-id="c429f-117">Usage</span></span>  
 <span data-ttu-id="c429f-118">`Iterator` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c429f-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
- [<span data-ttu-id="c429f-119">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="c429f-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [<span data-ttu-id="c429f-120">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="c429f-120">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="c429f-121">例</span><span class="sxs-lookup"><span data-stu-id="c429f-121">Example</span></span>  
 <span data-ttu-id="c429f-122">次の例は、反復子メソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="c429f-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="c429f-123">Iterator 関数には、For... の内部にある `Yield` ステートメントがあります。 [次](../../../visual-basic/language-reference/statements/for-next-statement.md)のループ。</span><span class="sxs-lookup"><span data-stu-id="c429f-123">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="c429f-124">`Main` 内の[各](../../../visual-basic/language-reference/statements/for-each-next-statement.md)ステートメント本体の各反復処理では、`Power` iterator 関数の呼び出しが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c429f-124">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="c429f-125">Iterator 関数を呼び出すごとに、`Yield` ステートメントの次の実行に進みます。これは、`For…Next` ループの次の反復処理で行われます。</span><span class="sxs-lookup"><span data-stu-id="c429f-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="c429f-126">例</span><span class="sxs-lookup"><span data-stu-id="c429f-126">Example</span></span>  
 <span data-ttu-id="c429f-127">次の例は、反復子である `Get` アクセサーを示しています。</span><span class="sxs-lookup"><span data-stu-id="c429f-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="c429f-128">`Iterator` 修飾子は、プロパティ宣言にあります。</span><span class="sxs-lookup"><span data-stu-id="c429f-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="c429f-129">その他の例については、「[反復子](../../programming-guide/concepts/iterators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c429f-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c429f-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="c429f-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [<span data-ttu-id="c429f-131">反復子</span><span class="sxs-lookup"><span data-stu-id="c429f-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="c429f-132">Yield ステートメント</span><span class="sxs-lookup"><span data-stu-id="c429f-132">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
