---
title: new 演算子
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
ms.openlocfilehash: 27b5b4516ef729045036c36fedc24b6c576a4f61
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348314"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="f3e89-102">New 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3e89-102">New Operator (Visual Basic)</span></span>

<span data-ttu-id="f3e89-103">新しいオブジェクト インスタンスを作成するための `New` 句の導入、型パラメーターでのコンストラクター制約の指定、またはクラス コンストラクターとして `Sub` プロシージャの指定を行います。</span><span class="sxs-lookup"><span data-stu-id="f3e89-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>

## <a name="remarks"></a><span data-ttu-id="f3e89-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3e89-104">Remarks</span></span>

<span data-ttu-id="f3e89-105">宣言または代入ステートメントで、`New` 句によって、インスタンスの作成元として使用できる定義済みのクラスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3e89-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="f3e89-106">つまり、このクラスによって、呼び出し元のコードがアクセスできる 1 つ以上のコンストラクターが公開されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f3e89-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>

<span data-ttu-id="f3e89-107">`New` 句は、宣言ステートメントまたは代入ステートメントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3e89-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="f3e89-108">このステートメントが実行されると、指定したクラスの適切なコンストラクターが呼び出され、指定した引数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="f3e89-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="f3e89-109">これを示す例を次に紹介します。2 つのコンストラクターがある `Customer` クラスのインスタンスを作成し、コンストラクターの 1 つはパラメーターを受け取らず、もう 1 つは文字列パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f3e89-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span></span>

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

<span data-ttu-id="f3e89-110">配列はクラスであるため、次の例に示すように、`New` によって新しい配列インスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f3e89-110">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span></span>

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

<span data-ttu-id="f3e89-111">新しいインスタンスを作成するためのメモリが不足している場合、共通言語ランタイム (CLR) は <xref:System.OutOfMemoryException> エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="f3e89-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>

> [!NOTE]
> <span data-ttu-id="f3e89-112">`New` キーワードを型パラメーター リストで使用して、指定した型が、アクセス可能なパラメーターなしのコンストラクターを公開する必要があること指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3e89-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="f3e89-113">型パラメーターと制約の詳細については、「[型リスト](../statements/type-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3e89-113">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span></span>

<span data-ttu-id="f3e89-114">クラスのコンストラクター プロシージャを作成するには、`Sub` プロシージャの名前を `New` キーワードに設定します。</span><span class="sxs-lookup"><span data-stu-id="f3e89-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="f3e89-115">詳細については、以下をご覧ください: [オブジェクトの有効期間: オブジェクトの作成と破棄](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)</span><span class="sxs-lookup"><span data-stu-id="f3e89-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

<span data-ttu-id="f3e89-116">キーワード `New` は次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3e89-116">The `New` keyword can be used in these contexts:</span></span>

- [<span data-ttu-id="f3e89-117">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3e89-117">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="f3e89-118">Of</span><span class="sxs-lookup"><span data-stu-id="f3e89-118">Of</span></span>](../statements/of-clause.md)
- [<span data-ttu-id="f3e89-119">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3e89-119">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="f3e89-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3e89-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="f3e89-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="f3e89-121">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="f3e89-122">型リスト</span><span class="sxs-lookup"><span data-stu-id="f3e89-122">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="f3e89-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3e89-123">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="f3e89-124">オブジェクトの有効期間: オブジェクトの作成と破棄</span><span class="sxs-lookup"><span data-stu-id="f3e89-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
