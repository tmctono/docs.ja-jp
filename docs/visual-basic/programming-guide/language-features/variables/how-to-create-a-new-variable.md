---
title: '方法: 新しい変数 (Visual Basic) を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: ee1e93b4e9819992f17738eb024004a4d66210d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332587"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="162bb-102">方法: 新しい変数 (Visual Basic) を作成します。</span><span class="sxs-lookup"><span data-stu-id="162bb-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="162bb-103">変数を作成する、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="162bb-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="162bb-104">新しい変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="162bb-104">To create a new variable</span></span>  
  
1. <span data-ttu-id="162bb-105">変数を宣言、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="162bb-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2. <span data-ttu-id="162bb-106">変数の特性の仕様を含める[プライベート](../../../../visual-basic/language-reference/modifiers/private.md)、[静的](../../../../visual-basic/language-reference/modifiers/static.md)、 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)、または[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)します。</span><span class="sxs-lookup"><span data-stu-id="162bb-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="162bb-107">詳細については、次を参照してください。[宣言された要素の特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)します。</span><span class="sxs-lookup"><span data-stu-id="162bb-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="162bb-108">必要はありません、`Dim`の宣言でその他のキーワードを使用する場合は、キーワード。</span><span class="sxs-lookup"><span data-stu-id="162bb-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3. <span data-ttu-id="162bb-109">Visual Basic の規則と規則に従う必要があります、変数の名前を持つ仕様に従ってください。</span><span class="sxs-lookup"><span data-stu-id="162bb-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="162bb-110">詳細については、次を参照してください。 [宣言された要素の名前](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)</span><span class="sxs-lookup"><span data-stu-id="162bb-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4. <span data-ttu-id="162bb-111">名に続けて、[として](../../../../visual-basic/language-reference/statements/as-clause.md)変数のデータ型を指定する句。</span><span class="sxs-lookup"><span data-stu-id="162bb-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="162bb-112">既定値を使用して、データ型を指定しない場合:`Object`します。</span><span class="sxs-lookup"><span data-stu-id="162bb-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5. <span data-ttu-id="162bb-113">に従って、`As`句に等号 (`=`) し、変数の初期値を等号 (=) に従います。</span><span class="sxs-lookup"><span data-stu-id="162bb-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     <span data-ttu-id="162bb-114">Visual Basic が実行されるたびに、変数に指定した値を割り当て、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="162bb-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="162bb-115">含むコードが最初に入ると、Visual Basic で、変数のデータ型の既定の初期値が割り当てられます、初期値を指定しない場合、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="162bb-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="162bb-116">含めることによって、クラスのインスタンスを作成するには、変数が参照型である場合、 [New 演算子](../../../../visual-basic/language-reference/operators/new-operator.md)キーワード、`As`句。</span><span class="sxs-lookup"><span data-stu-id="162bb-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="162bb-117">使用しない場合`New`、変数の初期値は[Nothing](../../../../visual-basic/language-reference/nothing.md)します。</span><span class="sxs-lookup"><span data-stu-id="162bb-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="162bb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="162bb-118">See also</span></span>

- [<span data-ttu-id="162bb-119">変数</span><span class="sxs-lookup"><span data-stu-id="162bb-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="162bb-120">変数宣言</span><span class="sxs-lookup"><span data-stu-id="162bb-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="162bb-121">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="162bb-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="162bb-122">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="162bb-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="162bb-123">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="162bb-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="162bb-124">ステートメント</span><span class="sxs-lookup"><span data-stu-id="162bb-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="162bb-125">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="162bb-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="162bb-126">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="162bb-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
