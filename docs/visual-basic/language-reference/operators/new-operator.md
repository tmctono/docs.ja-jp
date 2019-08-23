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
ms.openlocfilehash: 36cf71529b1f81c27881638d788117222c37171d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955878"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="eae09-102">New 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eae09-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="eae09-103">では`New` 、新しいオブジェクトインスタンスを作成する句、型パラメーターにコンストラクター制約を指定する句、また`Sub`はプロシージャをクラスコンストラクターとして識別する句が導入されています。</span><span class="sxs-lookup"><span data-stu-id="eae09-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eae09-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="eae09-104">Remarks</span></span>  
 <span data-ttu-id="eae09-105">宣言または代入ステートメント`New`では、句で、インスタンスを作成できる定義済みのクラスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae09-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="eae09-106">これは、クラスが、呼び出し元のコードがアクセスできる1つ以上のコンストラクターを公開する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="eae09-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="eae09-107">`New`句は、宣言ステートメントまたは代入ステートメントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="eae09-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="eae09-108">ステートメントを実行すると、指定したクラスの適切なコンストラクターが呼び出され、指定した引数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="eae09-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="eae09-109">次の例では、2つのコンストラクター `Customer`を持つクラスのインスタンスを作成します。1つはパラメーターを取らず、もう1つは文字列パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="eae09-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 <span data-ttu-id="eae09-110">配列はクラスである`New`ため、次の例に示すように、は新しい配列インスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="eae09-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 <span data-ttu-id="eae09-111">新しいインスタンスを作成するためのメモリが<xref:System.OutOfMemoryException>不足している場合は、共通言語ランタイム (CLR) によってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="eae09-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eae09-112">キーワード`New`は、指定された型がアクセス可能なパラメーターなしのコンストラクターを公開する必要があることを指定するために、型パラメーターリストでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="eae09-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="eae09-113">型パラメーターと制約の詳細については、「 [Type List](../../../visual-basic/language-reference/statements/type-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eae09-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="eae09-114">クラスのコンストラクタープロシージャを作成するには、 `Sub`プロシージャの名前を`New`キーワードに設定します。</span><span class="sxs-lookup"><span data-stu-id="eae09-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="eae09-115">詳細については[、次を参照してください。オブジェクトの有効期間:オブジェクトの作成方法と破棄](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)方法。</span><span class="sxs-lookup"><span data-stu-id="eae09-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="eae09-116">キーワード `New` は次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="eae09-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="eae09-117">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="eae09-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="eae09-118">Of</span><span class="sxs-lookup"><span data-stu-id="eae09-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="eae09-119">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="eae09-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="eae09-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="eae09-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="eae09-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="eae09-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="eae09-122">型リスト</span><span class="sxs-lookup"><span data-stu-id="eae09-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="eae09-123">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="eae09-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="eae09-124">オブジェクトの有効期間:オブジェクトの作成方法と破棄方法</span><span class="sxs-lookup"><span data-stu-id="eae09-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
