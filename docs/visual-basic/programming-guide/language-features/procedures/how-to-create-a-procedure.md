---
title: '方法: プロシージャを作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344907"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="04d9c-102">方法: プロシージャを作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04d9c-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="04d9c-103">プロシージャは、開始宣言ステートメント (`Sub` または `Function`) と終了宣言ステートメント (`End Sub` または `End Function`) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="04d9c-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="04d9c-104">プロシージャのコードはすべて、これらのステートメントの間にあります。</span><span class="sxs-lookup"><span data-stu-id="04d9c-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="04d9c-105">あるプロシージャに別のプロシージャを含めることはできないため、その開始と終了のステートメントは他のプロシージャの外部にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="04d9c-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="04d9c-106">異なる場所で同じタスクを実行するコードがある場合は、そのタスクをプロシージャとして一度記述してから、コード内の異なる場所から呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="04d9c-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="04d9c-107">値を返さないプロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="04d9c-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="04d9c-108">他のプロシージャの外部で、`Sub` ステートメントを使用し、その後に `End Sub` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="04d9c-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="04d9c-109">`Sub` ステートメントで、`Sub` キーワードの後にプロシージャの名前を指定してから、かっこで囲んだパラメーター リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="04d9c-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="04d9c-110">`Sub` および `End Sub` ステートメントの間に、プロシージャのコード ステートメントを配置します。</span><span class="sxs-lookup"><span data-stu-id="04d9c-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="04d9c-111">値を返すプロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="04d9c-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="04d9c-112">他のプロシージャの外部で、`Function` ステートメントを使用し、その後に `End Function` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="04d9c-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="04d9c-113">`Function` ステートメントで、`Function` キーワードの後にプロシージャの名前を指定します。次に、かっこで囲んだパラメーター リストを指定し、戻り値のデータ型を指定する `As` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="04d9c-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="04d9c-114">`Function` および `End Function` ステートメントの間に、プロシージャのコード ステートメントを配置します。</span><span class="sxs-lookup"><span data-stu-id="04d9c-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="04d9c-115">`Return` ステートメントを使用して、呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="04d9c-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="04d9c-116">新しいプロシージャを古い繰り返しコード ブロックに接続するには</span><span class="sxs-lookup"><span data-stu-id="04d9c-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="04d9c-117">古いコードでアクセスできる場所に新しいプロシージャを定義していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="04d9c-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="04d9c-118">古い繰り返しコード ブロックで、繰り返しタスクを実行するステートメントを、`Sub` または `Function` プロシージャを呼び出す単一のステートメントに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="04d9c-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="04d9c-119">プロシージャが、値を返す `Function` である場合は、呼び出し元のステートメントで確実に戻り値を持つアクション (変数に格納するなど) を実行するようにしてください。そうしないと、値が失われます。</span><span class="sxs-lookup"><span data-stu-id="04d9c-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="04d9c-120">例</span><span class="sxs-lookup"><span data-stu-id="04d9c-120">Example</span></span>

 <span data-ttu-id="04d9c-121">次の `Function` プロシージャでは、他の 2 つの辺の値を指定して、直角三角形の最も長い辺 (斜辺) を計算します。</span><span class="sxs-lookup"><span data-stu-id="04d9c-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="04d9c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="04d9c-122">See also</span></span>

- [<span data-ttu-id="04d9c-123">手順</span><span class="sxs-lookup"><span data-stu-id="04d9c-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="04d9c-124">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="04d9c-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="04d9c-125">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="04d9c-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="04d9c-126">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="04d9c-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="04d9c-127">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="04d9c-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="04d9c-128">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="04d9c-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="04d9c-129">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="04d9c-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="04d9c-130">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="04d9c-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="04d9c-131">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="04d9c-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="04d9c-132">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04d9c-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
