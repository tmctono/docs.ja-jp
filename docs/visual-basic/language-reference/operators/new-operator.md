---
title: New 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 630b0c48def77449f426b287a26f95af7cfb930e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936631"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="f6799-102">New 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6799-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="f6799-103">導入されています、 `New` 、新しいオブジェクト インスタンスを作成する句が、型パラメーターにコンス トラクター制約を指定または識別、`Sub`クラスのコンス トラクターと手順。</span><span class="sxs-lookup"><span data-stu-id="f6799-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6799-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="f6799-104">Remarks</span></span>  
 <span data-ttu-id="f6799-105">代入ステートメントの宣言で、`New`句は、定義済みクラスのインスタンスを作成できますを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6799-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="f6799-106">つまり、クラスが呼び出し元のコードにアクセスできる 1 つまたは複数のコンス トラクターを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6799-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="f6799-107">使用することができます、`New`宣言ステートメントまたは代入ステートメントの句。</span><span class="sxs-lookup"><span data-stu-id="f6799-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="f6799-108">ステートメントを実行すると、指定した引数を渡さず、指定したクラスの適切なコンス トラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f6799-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="f6799-109">次の例では、これを示しますのインスタンスを作成、`Customer`を 2 つのコンス トラクターを持つクラス、もう 1 つはパラメーターはとらず文字列パラメーターを受け取る。</span><span class="sxs-lookup"><span data-stu-id="f6799-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 <span data-ttu-id="f6799-110">配列は、クラスであるため`New`次の例に示すように、配列の新しいインスタンスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f6799-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 <span data-ttu-id="f6799-111">共通言語ランタイム (CLR) がスローされます、<xref:System.OutOfMemoryException>エラーの新しいインスタンスを作成する十分なメモリがある場合。</span><span class="sxs-lookup"><span data-stu-id="f6799-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6799-112">`New`キーワードが指定された型が、アクセス可能なパラメーターなしのコンス トラクターを公開する必要がありますを指定する型パラメーター リストで使用もします。</span><span class="sxs-lookup"><span data-stu-id="f6799-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="f6799-113">型パラメーターや制約の詳細については、次を参照してください。[型リスト](../../../visual-basic/language-reference/statements/type-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6799-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="f6799-114">クラスのコンス トラクターのプロシージャを作成するには、設定の名前、`Sub`する手順、`New`キーワード。</span><span class="sxs-lookup"><span data-stu-id="f6799-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="f6799-115">詳細については、次を参照してください。[オブジェクトの有効期間。オブジェクトの作成し、破棄方法](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6799-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="f6799-116">キーワード `New` は次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6799-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="f6799-117">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="f6799-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="f6799-118">Of</span><span class="sxs-lookup"><span data-stu-id="f6799-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="f6799-119">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="f6799-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f6799-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6799-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="f6799-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="f6799-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="f6799-122">型リスト</span><span class="sxs-lookup"><span data-stu-id="f6799-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="f6799-123">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="f6799-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="f6799-124">オブジェクトの有効期間:オブジェクトを作成および破棄する方法</span><span class="sxs-lookup"><span data-stu-id="f6799-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
