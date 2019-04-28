---
title: Visual Basic での変数宣言
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
ms.openlocfilehash: 699737ffbe0b136af8862931fadacec26772b928
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757002"
---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="538ff-102">Visual Basic での変数宣言</span><span class="sxs-lookup"><span data-stu-id="538ff-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="538ff-103">名前と特性を指定する変数を宣言するとします。</span><span class="sxs-lookup"><span data-stu-id="538ff-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="538ff-104">変数の宣言ステートメントは、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="538ff-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="538ff-105">その場所や内容は、変数の特性を決定します。</span><span class="sxs-lookup"><span data-stu-id="538ff-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="538ff-106">変数の名前付け規則と考慮事項では、次を参照してください。 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)します。</span><span class="sxs-lookup"><span data-stu-id="538ff-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="538ff-107">宣言レベル</span><span class="sxs-lookup"><span data-stu-id="538ff-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="538ff-108">ローカルとメンバー変数</span><span class="sxs-lookup"><span data-stu-id="538ff-108">Local and Member Variables</span></span>  
 <span data-ttu-id="538ff-109">*ローカル変数*はプロシージャ内で宣言されている 1 つです。</span><span class="sxs-lookup"><span data-stu-id="538ff-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="538ff-110">*メンバー変数* は、Visual Basic型のメンバーです。モジュール、クラス、構造体、またはモジュールの内部で宣言されていますが、そのクラス、構造体、またはモジュールの内部のプロシージャ内では宣言されていません。</span><span class="sxs-lookup"><span data-stu-id="538ff-110">A *member variable* is a member of a Visual Basic type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="538ff-111">共有し、インスタンス変数</span><span class="sxs-lookup"><span data-stu-id="538ff-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="538ff-112">クラスまたは構造体メンバー変数のカテゴリが共有されるかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="538ff-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="538ff-113">宣言されている場合、 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)キーワードは、*共有変数*、クラスまたは構造体のすべてのインスタンス間で共有される 1 つのコピーに存在するとします。</span><span class="sxs-lookup"><span data-stu-id="538ff-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="538ff-114">それ以外の場合は、*インスタンス変数*、クラスまたは構造体のインスタンスごとに個別のコピーが作成されたとします。</span><span class="sxs-lookup"><span data-stu-id="538ff-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="538ff-115">インスタンス変数のコピーは、クラスまたは構造体が作成されたインスタンスでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="538ff-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="538ff-116">これは、他のクラスまたは構造体のインスタンス、インスタンス変数のコピーを依存しません。</span><span class="sxs-lookup"><span data-stu-id="538ff-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="538ff-117">データ型の宣言</span><span class="sxs-lookup"><span data-stu-id="538ff-117">Declaring Data Type</span></span>  
 <span data-ttu-id="538ff-118">[として](../../../../visual-basic/language-reference/statements/as-clause.md)宣言ステートメントの句では、データ型またはオブジェクトを宣言する変数の種類を定義できます。</span><span class="sxs-lookup"><span data-stu-id="538ff-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="538ff-119">変数の種類として次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="538ff-119">You can specify any of the following types for a variable:</span></span>  
  
- <span data-ttu-id="538ff-120">などの基本のデータ入力`Boolean`、 `Long`、または `Decimal`</span><span class="sxs-lookup"><span data-stu-id="538ff-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
- <span data-ttu-id="538ff-121">配列や構造体などの複合データ型</span><span class="sxs-lookup"><span data-stu-id="538ff-121">A composite data type, such as an array or structure</span></span>  
  
- <span data-ttu-id="538ff-122">オブジェクトの種類、または、アプリケーションで、または別のアプリケーションで定義されているクラス</span><span class="sxs-lookup"><span data-stu-id="538ff-122">An object type, or class, defined either in your application or in another application</span></span>  
  
- <span data-ttu-id="538ff-123">A[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]クラスなど、<xref:System.Windows.Forms.Label>または <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="538ff-123">A [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
- <span data-ttu-id="538ff-124">インターフェイス型など、<xref:System.IComparable>または <xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="538ff-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="538ff-125">データ型を繰り返すことがなく、1 つのステートメントで複数の変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="538ff-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="538ff-126">次のステートメントでは、変数で`i`、 `j`、および`k`型として宣言されている`Integer`、`l`と`m`として`Long`と`x`と`y`として`Single`:</span><span class="sxs-lookup"><span data-stu-id="538ff-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="538ff-127">データ型の詳細については、次を参照してください。[データ型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="538ff-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="538ff-128">オブジェクトの詳細については、次を参照してください。[オブジェクトとクラス](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)と[コンポーネントによるプログラミング](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120))します。</span><span class="sxs-lookup"><span data-stu-id="538ff-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="538ff-129">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="538ff-129">Local Type Inference</span></span>  
 <span data-ttu-id="538ff-130">*型の推論*なしで宣言されたローカル変数のデータの種類を決定するために使用する`As`句。</span><span class="sxs-lookup"><span data-stu-id="538ff-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="538ff-131">コンパイラでは、初期化式の型から変数の型を推測します。</span><span class="sxs-lookup"><span data-stu-id="538ff-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="538ff-132">これにより、型を明示的に指定せずに変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="538ff-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="538ff-133">次の例では、どちらも`num1`と`num2`整数として厳密に型指定します。</span><span class="sxs-lookup"><span data-stu-id="538ff-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 <span data-ttu-id="538ff-134">ローカル型の推論を使用したい場合`Option Infer`に設定する必要があります`On`します。</span><span class="sxs-lookup"><span data-stu-id="538ff-134">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="538ff-135">詳細については、「[ローカル型の推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」と「[Option Infer ステートメント](../../../../visual-basic/language-reference/statements/option-infer-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="538ff-135">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="538ff-136">宣言された変数の特性</span><span class="sxs-lookup"><span data-stu-id="538ff-136">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="538ff-137">*有効期間*変数は、一定期間その中に、使用可能です。</span><span class="sxs-lookup"><span data-stu-id="538ff-137">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="538ff-138">一般に、変数は、(手順やクラスで) 宣言された要素が存在し続けます限り存在します。</span><span class="sxs-lookup"><span data-stu-id="538ff-138">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="538ff-139">変数がそのコンテナー要素の有効期間よりも長く必要がない場合は、宣言で特別な処理は必要はありません。</span><span class="sxs-lookup"><span data-stu-id="538ff-139">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="538ff-140">変数をそのコンテナー要素よりも長い場合は、含めることができます、`Static`または`Shared`キーワードでその`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="538ff-140">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="538ff-141">詳細については、次を参照してください。 [Visual Basic での有効期間](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)します。</span><span class="sxs-lookup"><span data-stu-id="538ff-141">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="538ff-142">*スコープ*変数がその名前を修飾せずに参照できるすべてのコードのセット。</span><span class="sxs-lookup"><span data-stu-id="538ff-142">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="538ff-143">変数のスコープは、宣言されている場所によって決まります。</span><span class="sxs-lookup"><span data-stu-id="538ff-143">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="538ff-144">特定のリージョン内にあるコードでは、その名前を修飾することがなく、そのリージョンで定義されている変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="538ff-144">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="538ff-145">詳細については、「 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="538ff-145">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="538ff-146">変数の*アクセス レベル*は、それへのアクセス許可があるコードの範囲です。</span><span class="sxs-lookup"><span data-stu-id="538ff-146">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="538ff-147">これは、`Dim`ステートメントで使用するアクセス修飾子([Public](../../../../visual-basic/language-reference/modifiers/public.md)または[Private](../../../../visual-basic/language-reference/modifiers/private.md)など)によって決まります。</span><span class="sxs-lookup"><span data-stu-id="538ff-147">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="538ff-148">詳細については、[ Visual Basic のアクセス レベル](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="538ff-148">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538ff-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="538ff-149">See also</span></span>

- [<span data-ttu-id="538ff-150">方法: 新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="538ff-150">How to: Create a New Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)
- [<span data-ttu-id="538ff-151">方法: および、変数からのデータを移動します。</span><span class="sxs-lookup"><span data-stu-id="538ff-151">How to: Move Data Into and Out of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="538ff-152">データの種類</span><span class="sxs-lookup"><span data-stu-id="538ff-152">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="538ff-153">Protected</span><span class="sxs-lookup"><span data-stu-id="538ff-153">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="538ff-154">Friend</span><span class="sxs-lookup"><span data-stu-id="538ff-154">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="538ff-155">Static</span><span class="sxs-lookup"><span data-stu-id="538ff-155">Static</span></span>](../../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="538ff-156">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="538ff-156">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="538ff-157">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="538ff-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="538ff-158">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="538ff-158">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
