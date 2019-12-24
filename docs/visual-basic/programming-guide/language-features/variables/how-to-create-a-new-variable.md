---
title: '方法 : 新しい変数を作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 2a2b5b8bef3b66f9727f0e65b61882186c007e94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353631"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="19072-102">方法: 新しい変数を作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19072-102">How to: Create a New Variable (Visual Basic)</span></span>

<span data-ttu-id="19072-103">変数を作成するには、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="19072-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

### <a name="to-create-a-new-variable"></a><span data-ttu-id="19072-104">新しい変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="19072-104">To create a new variable</span></span>

1. <span data-ttu-id="19072-105">`Dim` ステートメントで変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="19072-105">Declare the variable in a `Dim` statement.</span></span>

    ```vb
    Dim newCustomer
    ```

2. <span data-ttu-id="19072-106">[Private](../../../../visual-basic/language-reference/modifiers/private.md)、 [Static](../../../../visual-basic/language-reference/modifiers/static.md)、 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)、 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)など、変数の特性の仕様を含めます。</span><span class="sxs-lookup"><span data-stu-id="19072-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="19072-107">詳細については、「[宣言された要素の特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19072-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

    <span data-ttu-id="19072-108">宣言で他のキーワードを使用する場合、`Dim` キーワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="19072-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>

3. <span data-ttu-id="19072-109">仕様に従って変数の名前を指定します。これは Visual Basic の規則と規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="19072-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="19072-110">詳細については、「[宣言された要素の名前](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19072-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

4. <span data-ttu-id="19072-111">名前の後に As 句を使用し[て](../../../../visual-basic/language-reference/statements/as-clause.md)、変数のデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="19072-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>

    ```vb
    Public Static newCustomer As Customer
    ```

    <span data-ttu-id="19072-112">データ型を指定しない場合、既定値の `Object`が使用されます。</span><span class="sxs-lookup"><span data-stu-id="19072-112">If you do not specify the data type, it uses the default: `Object`.</span></span>

5. <span data-ttu-id="19072-113">`As` 句に等号 (`=`) を付けて、等号に続けて変数の初期値を指定します。</span><span class="sxs-lookup"><span data-stu-id="19072-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>

    <span data-ttu-id="19072-114">Visual Basic は、`Dim` ステートメントを実行するたびに、指定された値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="19072-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="19072-115">初期値を指定しなかった場合、`Dim` ステートメントを含むコードを最初に入力したときに、変数のデータ型の既定の初期値が Visual Basic に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="19072-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>

    <span data-ttu-id="19072-116">変数が参照型の場合は、`As` 句に[New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)キーワードを含めることで、そのクラスのインスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="19072-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="19072-117">`New`を使用しない場合、変数の初期値は[Nothing](../../../../visual-basic/language-reference/nothing.md)です。</span><span class="sxs-lookup"><span data-stu-id="19072-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a><span data-ttu-id="19072-118">参照</span><span class="sxs-lookup"><span data-stu-id="19072-118">See also</span></span>

- [<span data-ttu-id="19072-119">変数</span><span class="sxs-lookup"><span data-stu-id="19072-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="19072-120">変数宣言</span><span class="sxs-lookup"><span data-stu-id="19072-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="19072-121">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="19072-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="19072-122">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="19072-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="19072-123">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="19072-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="19072-124">ステートメント</span><span class="sxs-lookup"><span data-stu-id="19072-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="19072-125">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="19072-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="19072-126">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="19072-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
