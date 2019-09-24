---
title: '方法: プロシージャを作成する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216724"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="f6771-102">方法: プロシージャを作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6771-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="f6771-103">開始`Sub`宣言ステートメント (または`Function`) と終了宣言ステートメント (`End Sub`または`End Function`) の間でプロシージャを囲みます。</span><span class="sxs-lookup"><span data-stu-id="f6771-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="f6771-104">すべてのプロシージャのコードは、これらのステートメントの間にあります。</span><span class="sxs-lookup"><span data-stu-id="f6771-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="f6771-105">プロシージャに別のプロシージャを含めることはできません。そのため、プロシージャの開始と終了のステートメントを他のプロシージャの外側に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6771-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="f6771-106">異なる場所で同じタスクを実行するコードがある場合は、そのタスクを1回のプロシージャとして記述し、コード内のさまざまな場所から呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f6771-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="f6771-107">値を返さないプロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="f6771-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="f6771-108">他のプロシージャの外部では`Sub` 、ステートメント`End Sub`とステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6771-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="f6771-109">ステートメントで、 `Sub`キーワードに続けてプロシージャの名前を指定し、その後にパラメーターリストをかっこで囲んで指定します。 `Sub`</span><span class="sxs-lookup"><span data-stu-id="f6771-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="f6771-110">プロシージャのコードステートメントをステートメント`Sub`と`End Sub`ステートメントの間に配置します。</span><span class="sxs-lookup"><span data-stu-id="f6771-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="f6771-111">値を返すプロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="f6771-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="f6771-112">他のプロシージャの外部では`Function` 、ステートメント`End Function`とステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6771-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="f6771-113">ステートメントで、 `Function`キーワードに続けてプロシージャの名前を指定し、次に`As`かっこで囲んだパラメーターリストを指定し、次に戻り値のデータ型を指定する句を指定します。 `Function`</span><span class="sxs-lookup"><span data-stu-id="f6771-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="f6771-114">プロシージャのコードステートメントをステートメント`Function`と`End Function`ステートメントの間に配置します。</span><span class="sxs-lookup"><span data-stu-id="f6771-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="f6771-115">ステートメントを`Return`使用して、呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="f6771-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="f6771-116">新しいプロシージャを古い繰り返しのコードブロックに接続するには</span><span class="sxs-lookup"><span data-stu-id="f6771-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="f6771-117">古いコードがアクセスできる場所に新しいプロシージャを定義していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6771-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="f6771-118">繰り返し実行されるコードブロックで、反復するタスクを実行するステートメントを、 `Sub`または`Function`プロシージャを呼び出す1つのステートメントに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f6771-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="f6771-119">プロシージャが値を返す`Function`である場合は、呼び出し元のステートメントが戻り値を持つアクション (変数に格納するなど) を実行していることを確認してください。そうでない場合、値は失われます。</span><span class="sxs-lookup"><span data-stu-id="f6771-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="f6771-120">例</span><span class="sxs-lookup"><span data-stu-id="f6771-120">Example</span></span>

 <span data-ttu-id="f6771-121">次`Function`の手順では、直角三角形の最長の辺 (斜辺) を計算します。これは、他の2つの辺の値を指定したものです。</span><span class="sxs-lookup"><span data-stu-id="f6771-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="f6771-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6771-122">See also</span></span>

- [<span data-ttu-id="f6771-123">手順</span><span class="sxs-lookup"><span data-stu-id="f6771-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="f6771-124">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f6771-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="f6771-125">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f6771-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="f6771-126">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f6771-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="f6771-127">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f6771-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="f6771-128">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="f6771-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f6771-129">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f6771-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="f6771-130">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="f6771-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="f6771-131">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="f6771-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="f6771-132">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6771-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
