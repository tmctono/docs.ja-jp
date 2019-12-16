---
title: 変数宣言
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: b89773e9527af0d65cde53b61654f2511f5c8dde
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351759"
---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="a2508-102">Visual Basic での変数宣言</span><span class="sxs-lookup"><span data-stu-id="a2508-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="a2508-103">変数を宣言して、その名前と特性を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2508-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="a2508-104">変数の宣言ステートメントは、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)です。</span><span class="sxs-lookup"><span data-stu-id="a2508-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="a2508-105">その場所と内容によって、変数の特性が決まります。</span><span class="sxs-lookup"><span data-stu-id="a2508-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="a2508-106">変数の名前付け規則と考慮事項については、「宣言された[要素名](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2508-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="a2508-107">宣言レベル</span><span class="sxs-lookup"><span data-stu-id="a2508-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="a2508-108">ローカル変数とメンバー変数</span><span class="sxs-lookup"><span data-stu-id="a2508-108">Local and Member Variables</span></span>  
 <span data-ttu-id="a2508-109">*ローカル変数*は、プロシージャ内で宣言されています。</span><span class="sxs-lookup"><span data-stu-id="a2508-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="a2508-110">*メンバー変数*は Visual Basic 型のメンバーです。これは、モジュールレベルで、クラス、構造体、またはモジュールの内部で宣言されますが、そのクラス、構造体、またはモジュールの内部のプロシージャ内では宣言されません。</span><span class="sxs-lookup"><span data-stu-id="a2508-110">A *member variable* is a member of a Visual Basic type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="a2508-111">共有変数とインスタンス変数</span><span class="sxs-lookup"><span data-stu-id="a2508-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="a2508-112">クラスまたは構造体では、メンバー変数のカテゴリは、そのメンバーが共有されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a2508-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="a2508-113">[Shared](../../../../visual-basic/language-reference/modifiers/shared.md)キーワードを使用して宣言されている場合、これは*共有変数*であり、クラスまたは構造体のすべてのインスタンス間で共有される1つのコピーに存在します。</span><span class="sxs-lookup"><span data-stu-id="a2508-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="a2508-114">それ以外の場合は、*インスタンス変数*になり、クラスまたは構造体のインスタンスごとに個別のコピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2508-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="a2508-115">インスタンス変数の特定のコピーは、それが作成されたクラスまたは構造体のインスタンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2508-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="a2508-116">これは、クラスまたは構造体の他のインスタンスのインスタンス変数のコピーとは無関係です。</span><span class="sxs-lookup"><span data-stu-id="a2508-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="a2508-117">データ型の宣言</span><span class="sxs-lookup"><span data-stu-id="a2508-117">Declaring Data Type</span></span>  
 <span data-ttu-id="a2508-118">宣言ステートメントの As 句を使用する[と](../../../../visual-basic/language-reference/statements/as-clause.md)、宣言する変数のデータ型またはオブジェクト型を定義できます。</span><span class="sxs-lookup"><span data-stu-id="a2508-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="a2508-119">変数には、次のいずれかの型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a2508-119">You can specify any of the following types for a variable:</span></span>  
  
- <span data-ttu-id="a2508-120">`Boolean`、`Long`、`Decimal` などの基本データ型</span><span class="sxs-lookup"><span data-stu-id="a2508-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
- <span data-ttu-id="a2508-121">配列や構造体などの複合データ型</span><span class="sxs-lookup"><span data-stu-id="a2508-121">A composite data type, such as an array or structure</span></span>  
  
- <span data-ttu-id="a2508-122">アプリケーション内または別のアプリケーションで定義されているオブジェクトの種類 (クラス)。</span><span class="sxs-lookup"><span data-stu-id="a2508-122">An object type, or class, defined either in your application or in another application</span></span>  
  
- <span data-ttu-id="a2508-123"><xref:System.Windows.Forms.Label> や <xref:System.Windows.Forms.TextBox> などの .NET Framework クラス。</span><span class="sxs-lookup"><span data-stu-id="a2508-123">A .NET Framework class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
- <span data-ttu-id="a2508-124"><xref:System.IComparable> や <xref:System.IDisposable> などのインターフェイス型</span><span class="sxs-lookup"><span data-stu-id="a2508-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="a2508-125">1つのステートメントで複数の変数を宣言しても、データ型を繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a2508-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="a2508-126">次のステートメントでは、変数 `i`、`j`、および `k` を型 `Integer`、`l` として `m` として宣言し、`Long`として `x` します。`y``Single`</span><span class="sxs-lookup"><span data-stu-id="a2508-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```vb  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="a2508-127">データ型の詳細については、「[データ型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2508-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="a2508-128">オブジェクトの詳細については、「[オブジェクトとクラス](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)」および「[コンポーネントを使用したプログラミング](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2508-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="a2508-129">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="a2508-129">Local Type Inference</span></span>  
 <span data-ttu-id="a2508-130">*型の推定*は、`As` 句を使用せずに宣言されたローカル変数のデータ型を決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2508-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="a2508-131">コンパイラは、初期化式の型から変数の型を推測します。</span><span class="sxs-lookup"><span data-stu-id="a2508-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="a2508-132">これにより、型を明示的に指定せずに変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a2508-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="a2508-133">次の例では、`num1` と `num2` の両方が整数として厳密に型指定されています。</span><span class="sxs-lookup"><span data-stu-id="a2508-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 <span data-ttu-id="a2508-134">ローカル型の推論を使用する場合は、`Option Infer` を `On`に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2508-134">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="a2508-135">詳細については、「[ローカル型の推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」と「[Option Infer ステートメント](../../../../visual-basic/language-reference/statements/option-infer-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2508-135">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="a2508-136">宣言された変数の特性</span><span class="sxs-lookup"><span data-stu-id="a2508-136">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="a2508-137">変数の*有効*期間は、その期間内に使用できる期間です。</span><span class="sxs-lookup"><span data-stu-id="a2508-137">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="a2508-138">一般に、変数は、その変数を宣言する要素 (プロシージャやクラスなど) が引き続き存在する限り存在します。</span><span class="sxs-lookup"><span data-stu-id="a2508-138">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="a2508-139">変数に含まれる要素の有効期間が過ぎても既存の変数を続行する必要がない場合は、宣言で特別な操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a2508-139">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="a2508-140">変数が、それを含む要素よりも長く存在する必要がある場合は、`Dim` ステートメントに `Static` または `Shared` キーワードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a2508-140">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="a2508-141">詳細については、「 [Visual Basic の有効期間](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2508-141">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="a2508-142">変数の*スコープ*は、その名前を修飾せずに参照できるすべてのコードのセットです。</span><span class="sxs-lookup"><span data-stu-id="a2508-142">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="a2508-143">変数のスコープは、宣言されている場所によって決まります。</span><span class="sxs-lookup"><span data-stu-id="a2508-143">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="a2508-144">特定の地域にあるコードは、その領域で定義された変数を使用できますが、名前を修飾する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a2508-144">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="a2508-145">詳細については、「[Visual Basic におけるスコープ](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2508-145">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="a2508-146">変数の*アクセスレベル*は、それにアクセスするためのアクセス許可を持つコードの範囲です。</span><span class="sxs-lookup"><span data-stu-id="a2508-146">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="a2508-147">これは、`Dim` ステートメントで使用するアクセス修飾子 ( [Public](../../../../visual-basic/language-reference/modifiers/public.md) 、 [Private](../../../../visual-basic/language-reference/modifiers/private.md)など) によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="a2508-147">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="a2508-148">詳細については、「[Visual Basic でのアクセス レベル](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2508-148">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2508-149">参照</span><span class="sxs-lookup"><span data-stu-id="a2508-149">See also</span></span>

- [<span data-ttu-id="a2508-150">方法 : 新しい変数を作成する</span><span class="sxs-lookup"><span data-stu-id="a2508-150">How to: Create a New Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)
- [<span data-ttu-id="a2508-151">方法 : 変数に値を格納する、および変数から値を取得する</span><span class="sxs-lookup"><span data-stu-id="a2508-151">How to: Move Data Into and Out of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="a2508-152">データの種類</span><span class="sxs-lookup"><span data-stu-id="a2508-152">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a2508-153">Protected</span><span class="sxs-lookup"><span data-stu-id="a2508-153">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="a2508-154">Friend</span><span class="sxs-lookup"><span data-stu-id="a2508-154">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="a2508-155">Static</span><span class="sxs-lookup"><span data-stu-id="a2508-155">Static</span></span>](../../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="a2508-156">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="a2508-156">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="a2508-157">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="a2508-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="a2508-158">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="a2508-158">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
