---
title: '方法: 新しい変数を作成する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: a6cb7225ea203f0b38b731795684bfb0cfdfd2d1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630902"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="844da-102">方法: 新しい変数を作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="844da-102">How to: Create a New Variable (Visual Basic)</span></span>

<span data-ttu-id="844da-103">変数を作成するには、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="844da-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

### <a name="to-create-a-new-variable"></a><span data-ttu-id="844da-104">新しい変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="844da-104">To create a new variable</span></span>

1. <span data-ttu-id="844da-105">`Dim`ステートメントで変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="844da-105">Declare the variable in a `Dim` statement.</span></span>

    ```vb
    Dim newCustomer
    ```

2. <span data-ttu-id="844da-106">[Private](../../../../visual-basic/language-reference/modifiers/private.md)、 [Static](../../../../visual-basic/language-reference/modifiers/static.md)、 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)、 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)など、変数の特性の仕様を含めます。</span><span class="sxs-lookup"><span data-stu-id="844da-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="844da-107">詳細については、「宣言された[要素の特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="844da-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

    <span data-ttu-id="844da-108">宣言で他のキーワード`Dim`を使用する場合、キーワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="844da-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>

3. <span data-ttu-id="844da-109">仕様に従って変数の名前を指定します。これは Visual Basic の規則と規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="844da-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="844da-110">詳細については、次を参照してください。 [宣言された要素の名前](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)</span><span class="sxs-lookup"><span data-stu-id="844da-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

4. <span data-ttu-id="844da-111">名前の後に As 句を使用し[て](../../../../visual-basic/language-reference/statements/as-clause.md)、変数のデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="844da-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>

    ```vb
    Public Static newCustomer As Customer
    ```

    <span data-ttu-id="844da-112">データ型を指定しない場合、既定値`Object`のが使用されます。</span><span class="sxs-lookup"><span data-stu-id="844da-112">If you do not specify the data type, it uses the default: `Object`.</span></span>

5. <span data-ttu-id="844da-113">句の`As`後に等号 (`=`) を付け、等号に続けて変数の初期値を指定します。</span><span class="sxs-lookup"><span data-stu-id="844da-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>

    <span data-ttu-id="844da-114">Visual Basic は、 `Dim`ステートメントを実行するたびに、指定された値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="844da-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="844da-115">初期値を指定しない場合、は、 `Dim`ステートメントが含まれているコードに最初に入力したときに、変数のデータ型の既定の初期値を Visual Basic 割り当てます。</span><span class="sxs-lookup"><span data-stu-id="844da-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>

    <span data-ttu-id="844da-116">変数が参照型の場合は、 `As`句に[New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)キーワードを含めることで、そのクラスのインスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="844da-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="844da-117">を使用`New`しない場合、変数の初期値は[Nothing](../../../../visual-basic/language-reference/nothing.md)です。</span><span class="sxs-lookup"><span data-stu-id="844da-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a><span data-ttu-id="844da-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="844da-118">See also</span></span>

- [<span data-ttu-id="844da-119">変数</span><span class="sxs-lookup"><span data-stu-id="844da-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="844da-120">変数宣言</span><span class="sxs-lookup"><span data-stu-id="844da-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="844da-121">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="844da-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="844da-122">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="844da-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="844da-123">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="844da-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="844da-124">ステートメント</span><span class="sxs-lookup"><span data-stu-id="844da-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="844da-125">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="844da-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="844da-126">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="844da-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
