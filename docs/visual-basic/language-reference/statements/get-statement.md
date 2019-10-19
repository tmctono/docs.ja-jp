---
title: Get ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: d76155b8ff29e4f5e9206ae8fc689fa4fcaf3b8c
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581827"
---
# <a name="get-statement"></a><span data-ttu-id="381bd-102">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="381bd-102">Get Statement</span></span>
<span data-ttu-id="381bd-103">プロパティの値を取得するために使用される `Get` プロパティプロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="381bd-103">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="381bd-104">構文</span><span class="sxs-lookup"><span data-stu-id="381bd-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="381bd-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="381bd-105">Parts</span></span>  
  
|<span data-ttu-id="381bd-106">用語</span><span class="sxs-lookup"><span data-stu-id="381bd-106">Term</span></span>|<span data-ttu-id="381bd-107">定義</span><span class="sxs-lookup"><span data-stu-id="381bd-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="381bd-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="381bd-108">Optional.</span></span> <span data-ttu-id="381bd-109">「[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="381bd-109">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="381bd-110">このプロパティの `Get` および `Set` ステートメントのうちの1つで、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="381bd-110">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="381bd-111">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="381bd-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="381bd-112">[保護されている](../../../visual-basic/language-reference/modifiers/protected.md)-   </span><span class="sxs-lookup"><span data-stu-id="381bd-112">-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)</span></span><br /><span data-ttu-id="381bd-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="381bd-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span></span><br /><span data-ttu-id="381bd-114">-   [プライベート](../../../visual-basic/language-reference/modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="381bd-114">-   [Private](../../../visual-basic/language-reference/modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="381bd-115">「 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="381bd-115">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="381bd-116">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="381bd-116">Optional.</span></span> <span data-ttu-id="381bd-117">@No__t_0 プロパティプロシージャが呼び出されたときに実行される1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="381bd-117">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="381bd-118">必須です。</span><span class="sxs-lookup"><span data-stu-id="381bd-118">Required.</span></span> <span data-ttu-id="381bd-119">@No__t_0 property プロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="381bd-119">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="381bd-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="381bd-120">Remarks</span></span>  
 <span data-ttu-id="381bd-121">プロパティが `WriteOnly` としてマークされている場合を除き、すべてのプロパティには `Get` プロパティプロシージャが必要です。</span><span class="sxs-lookup"><span data-stu-id="381bd-121">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="381bd-122">@No__t_0 プロシージャは、プロパティの現在の値を返すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="381bd-122">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="381bd-123">Visual Basic は、プロパティの値を式が要求すると、プロパティの `Get` プロシージャを自動的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="381bd-123">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="381bd-124">プロパティ宣言の本体には、プロパティの `Get` と、[プロパティステートメント](../../../visual-basic/language-reference/statements/property-statement.md)と `End Property` ステートメントの間の `Set` プロシージャのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="381bd-124">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="381bd-125">これらのプロシージャ以外を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="381bd-125">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="381bd-126">特に、プロパティの現在の値を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="381bd-126">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="381bd-127">この値はプロパティの外部に格納する必要があります。これは、プロパティプロシージャの内部に格納する場合、他のプロパティプロシージャがアクセスできないためです。</span><span class="sxs-lookup"><span data-stu-id="381bd-127">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="381bd-128">通常の方法では、プロパティと同じレベルで宣言された[プライベート](../../../visual-basic/language-reference/modifiers/private.md)変数に値を格納します。</span><span class="sxs-lookup"><span data-stu-id="381bd-128">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="381bd-129">@No__t_0 プロシージャは、適用先のプロパティ内で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="381bd-129">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="381bd-130">@No__t_2 ステートメントで `accessmodifier` を使用しない限り、`Get` プロシージャの既定値は、それを含むプロパティのアクセスレベルです。</span><span class="sxs-lookup"><span data-stu-id="381bd-130">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="381bd-131">ルール</span><span class="sxs-lookup"><span data-stu-id="381bd-131">Rules</span></span>  
  
- <span data-ttu-id="381bd-132">**混合アクセスレベル。**</span><span class="sxs-lookup"><span data-stu-id="381bd-132">**Mixed Access Levels.**</span></span> <span data-ttu-id="381bd-133">読み取り/書き込みプロパティを定義する場合は、必要に応じて、`Get` または `Set` のいずれかのプロシージャに対して異なるアクセスレベルを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="381bd-133">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="381bd-134">この場合、プロシージャのアクセスレベルは、プロパティのアクセスレベルよりも制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="381bd-134">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="381bd-135">たとえば、プロパティが `Friend` として宣言されている場合は、`Get` プロシージャ `Private` を宣言できますが、`Public` は宣言できません。</span><span class="sxs-lookup"><span data-stu-id="381bd-135">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="381bd-136">@No__t_0 プロパティを定義する場合、`Get` プロシージャはプロパティ全体を表します。</span><span class="sxs-lookup"><span data-stu-id="381bd-136">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="381bd-137">@No__t_0 に対して異なるアクセスレベルを宣言することはできません。これは、プロパティに2つのアクセスレベルが設定されるためです。</span><span class="sxs-lookup"><span data-stu-id="381bd-137">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
- <span data-ttu-id="381bd-138">**戻り値の型。**</span><span class="sxs-lookup"><span data-stu-id="381bd-138">**Return Type.**</span></span> <span data-ttu-id="381bd-139">[Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)では、返される値のデータ型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="381bd-139">The [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="381bd-140">@No__t_0 プロシージャは、そのデータ型を自動的に返します。</span><span class="sxs-lookup"><span data-stu-id="381bd-140">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="381bd-141">任意のデータ型を指定することも、列挙型、構造体、クラス、またはインターフェイスの名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="381bd-141">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="381bd-142">@No__t_0 ステートメントで `returntype` が指定されていない場合、プロシージャは `Object` を返します。</span><span class="sxs-lookup"><span data-stu-id="381bd-142">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="381bd-143">動作</span><span class="sxs-lookup"><span data-stu-id="381bd-143">Behavior</span></span>  
  
- <span data-ttu-id="381bd-144">**プロシージャからを返します。**</span><span class="sxs-lookup"><span data-stu-id="381bd-144">**Returning from a Procedure.**</span></span> <span data-ttu-id="381bd-145">@No__t_0 プロシージャが呼び出し元のコードに戻ると、プロパティ値を要求したステートメント内で実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="381bd-145">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="381bd-146">`Get` のプロパティプロシージャは、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)を使用するか、プロパティ名に戻り値を割り当てることによって、値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="381bd-146">`Get` property procedures can return a value using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="381bd-147">詳細については、「 [Function ステートメント](../../../visual-basic/language-reference/statements/function-statement.md)」の「戻り値」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="381bd-147">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="381bd-148">@No__t_0 ステートメントおよび `Return` ステートメントでは、プロパティプロシージャがすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="381bd-148">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="381bd-149">プロシージャ内の任意の場所で任意の数の `Exit Property` および `Return` ステートメントを使用できます。また、`Exit Property` と `Return` のステートメントを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="381bd-149">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
- <span data-ttu-id="381bd-150">**戻り値。**</span><span class="sxs-lookup"><span data-stu-id="381bd-150">**Return Value.**</span></span> <span data-ttu-id="381bd-151">@No__t_0 プロシージャから値を返すには、プロパティ名に値を割り当てるか、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="381bd-151">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span> <span data-ttu-id="381bd-152">@No__t_0 ステートメントでは、`Get` プロシージャの戻り値が同時に割り当てられ、プロシージャが終了します。</span><span class="sxs-lookup"><span data-stu-id="381bd-152">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="381bd-153">プロパティ名に値を割り当てずに `Exit Property` を使用する場合、`Get` プロシージャは、プロパティのデータ型の既定値を返します。</span><span class="sxs-lookup"><span data-stu-id="381bd-153">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="381bd-154">詳細については、「 [Function ステートメント](../../../visual-basic/language-reference/statements/function-statement.md)」の「戻り値」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="381bd-154">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="381bd-155">次の例は、読み取り専用プロパティ `quoteForTheDay` が、プライベート変数 `quoteValue` に保持されている値を返す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="381bd-155">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="381bd-156">例</span><span class="sxs-lookup"><span data-stu-id="381bd-156">Example</span></span>  
 <span data-ttu-id="381bd-157">次の例では、`Get` ステートメントを使用して、プロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="381bd-157">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="381bd-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="381bd-158">See also</span></span>

- [<span data-ttu-id="381bd-159">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="381bd-159">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="381bd-160">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="381bd-160">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="381bd-161">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="381bd-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="381bd-162">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="381bd-162">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="381bd-163">チュートリアル : クラスの定義</span><span class="sxs-lookup"><span data-stu-id="381bd-163">Walkthrough: Defining Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
