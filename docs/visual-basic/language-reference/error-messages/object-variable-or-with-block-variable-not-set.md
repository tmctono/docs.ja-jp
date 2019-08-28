---
title: オブジェクト変数または With ブロック変数が設定されていません。
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 07c215d373e4ac1cbadf82a48b8cb3d90efdbdb4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040555"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="1ee9b-102">オブジェクト変数または With ブロック変数が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="1ee9b-103">無効なオブジェクト変数が参照されています。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="1ee9b-104">このエラーが発生する原因は複数あります。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-104">This error can occur for several reasons:</span></span>

- <span data-ttu-id="1ee9b-105">型を指定せずに変数が宣言されました。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="1ee9b-106">変数が型を指定せずに宣言されている場合`Object`、既定値は型になります。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="1ee9b-107">たとえば、で`Dim x`宣言さ`String`れた変数の型は`Object;` 、で`Dim x As String`宣言された変数の型になります。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    > <span data-ttu-id="1ee9b-108">ステートメント`Option Strict`では、 `Object`型を生成する暗黙的な型指定が禁止されています。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="1ee9b-109">型を省略すると、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="1ee9b-110">「 [Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="1ee9b-111">に`Nothing`設定されているオブジェクトを参照しようとしています。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-111">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="1ee9b-112">正しく宣言されていない配列変数の要素にアクセスしようとしています。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-112">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="1ee9b-113">たとえば、として`products() As String`宣言された配列は、配列`products(3) = "Widget"`の要素を参照しようとした場合にエラーをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-113">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="1ee9b-114">配列には要素がなく、オブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-114">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="1ee9b-115">ブロックが初期化される前に、 `With...End With`ブロック内のコードにアクセスしようとしています。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-115">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="1ee9b-116">ブロック`With...End With`は、ステートメントの`With`エントリポイントを実行して初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-116">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="1ee9b-117">以前のバージョンの Visual Basic または VBA では、このエラーは、 `Set` (`x = "name"`では`Set x = "name"`なく) キーワードを使用せずに変数に値を割り当てることによってもトリガーされました。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-117">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="1ee9b-118">キーワード`Set`は Visual Basic .net では無効になりました。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-118">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1ee9b-119">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1ee9b-119">To correct this error</span></span>

1. <span data-ttu-id="1ee9b-120">ファイル`Option Strict`の`On`先頭に次のコードを追加することにより、をに設定します。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-120">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="1ee9b-121">プロジェクトを実行すると、型が指定されていない変数の**エラー一覧**にコンパイラエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-121">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="1ee9b-122">を有効`Option Strict`にしない場合は、(`Dim x`では`Dim x As String`なく) 型を指定せずに指定された変数をコードで検索し、目的の型を宣言に追加します。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="1ee9b-123">に`Nothing`設定されているオブジェクト変数を参照していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="1ee9b-124">コード内でキーワード`Nothing`を検索し、参照するまでオブジェクトがに`Nothing`設定されないようにコードを修正します。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="1ee9b-125">配列変数にアクセスする前に、それらの変数を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="1ee9b-126">最初に配列を作成するときに (`Dim x(5) As String`では`Dim x() As String`なく`ReDim` ) ディメンションを割り当てるか、またはキーワードを使用して、最初に配列にアクセスする前に配列の次元を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="1ee9b-127">ステートメントの`With` `With`エントリポイントを実行して、ブロックが初期化されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ee9b-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ee9b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ee9b-128">See also</span></span>

- [<span data-ttu-id="1ee9b-129">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="1ee9b-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="1ee9b-130">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="1ee9b-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="1ee9b-131">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="1ee9b-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
