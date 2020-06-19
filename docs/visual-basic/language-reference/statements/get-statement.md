---
title: Get ステートメント
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
ms.openlocfilehash: 31936fb2c8f658203a43702a2b5fa4ee2481beb5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404603"
---
# <a name="get-statement"></a><span data-ttu-id="6676b-102">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="6676b-102">Get Statement</span></span>
<span data-ttu-id="6676b-103">プロパティの値を取得するために使用する `Get` プロパティ プロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="6676b-103">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6676b-104">構文</span><span class="sxs-lookup"><span data-stu-id="6676b-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="6676b-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="6676b-105">Parts</span></span>  
  
|<span data-ttu-id="6676b-106">用語</span><span class="sxs-lookup"><span data-stu-id="6676b-106">Term</span></span>|<span data-ttu-id="6676b-107">定義</span><span class="sxs-lookup"><span data-stu-id="6676b-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="6676b-108">任意。</span><span class="sxs-lookup"><span data-stu-id="6676b-108">Optional.</span></span> <span data-ttu-id="6676b-109">「[属性リスト](attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6676b-109">See [Attribute List](attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="6676b-110">このプロパティの `Get` および `Set` ステートメントのいずれかで、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6676b-110">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="6676b-111">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6676b-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="6676b-112">-   [Protected](../modifiers/protected.md)</span><span class="sxs-lookup"><span data-stu-id="6676b-112">-   [Protected](../modifiers/protected.md)</span></span><br /><span data-ttu-id="6676b-113">-   [Friend](../modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="6676b-113">-   [Friend](../modifiers/friend.md)</span></span><br /><span data-ttu-id="6676b-114">-   [Private](../modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="6676b-114">-   [Private](../modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="6676b-115">「 [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6676b-115">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="6676b-116">任意。</span><span class="sxs-lookup"><span data-stu-id="6676b-116">Optional.</span></span> <span data-ttu-id="6676b-117">`Get` プロパティ プロシージャが呼び出されたときに実行される 1 つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="6676b-117">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="6676b-118">必須です。</span><span class="sxs-lookup"><span data-stu-id="6676b-118">Required.</span></span> <span data-ttu-id="6676b-119">`Get` プロパティ プロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="6676b-119">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6676b-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="6676b-120">Remarks</span></span>  
 <span data-ttu-id="6676b-121">プロパティが `WriteOnly` とマークされている場合を除き、すべてのプロパティには `Get` プロパティ プロシージャが必要です。</span><span class="sxs-lookup"><span data-stu-id="6676b-121">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="6676b-122">`Get` プロシージャは、プロパティの現在の値を返すために使用します。</span><span class="sxs-lookup"><span data-stu-id="6676b-122">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="6676b-123">Visual Basic では、式でプロパティの値が要求されると、プロパティの `Get` プロシージャが自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6676b-123">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="6676b-124">プロパティ宣言の本体には、[Property ステートメント](property-statement.md)と `End Property` ステートメントの間に、プロパティの `Get` と `Set` のプロシージャのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6676b-124">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="6676b-125">これらのプロシージャ以外のものを格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="6676b-125">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="6676b-126">特に、プロパティの現在の値を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="6676b-126">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="6676b-127">この値は、プロパティの外部に格納する必要があります。それをいずれかのプロパティ プロシージャの内部に格納した場合、他のプロパティ プロシージャからアクセスできなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="6676b-127">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="6676b-128">通常の方法は、プロパティと同じレベルで宣言された [Private](../modifiers/private.md) 変数に値を格納することです。</span><span class="sxs-lookup"><span data-stu-id="6676b-128">The usual approach is to store the value in a [Private](../modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="6676b-129">`Get` プロシージャは、適用先のプロパティの内部で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6676b-129">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="6676b-130">`Get` ステートメントで `accessmodifier` を使用しない限り、`Get` プロシージャは既定で、それを含んでいるプロパティのアクセス レベルに設定されます。</span><span class="sxs-lookup"><span data-stu-id="6676b-130">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="6676b-131">ルール</span><span class="sxs-lookup"><span data-stu-id="6676b-131">Rules</span></span>  
  
- <span data-ttu-id="6676b-132">**混合アクセス レベル。**</span><span class="sxs-lookup"><span data-stu-id="6676b-132">**Mixed Access Levels.**</span></span> <span data-ttu-id="6676b-133">読み取り/書き込みプロパティを定義する場合は、必要に応じて、`Get` または `Set` のいずれかのプロシージャに対して異なるアクセス レベルを指定できますが、両方に対して指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6676b-133">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="6676b-134">この場合、プロシージャのアクセス レベルは、プロパティのアクセス レベルよりも制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6676b-134">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="6676b-135">たとえば、プロパティが `Friend` として宣言されている場合は、`Get` プロシージャを、`Public` ではなく `Private` として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="6676b-135">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="6676b-136">`ReadOnly` プロパティを定義する場合、`Get` プロシージャはプロパティ全体を表します。</span><span class="sxs-lookup"><span data-stu-id="6676b-136">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="6676b-137">`Get` に対して異なるアクセス レベルを宣言することはできません。それによって、プロパティに 2 つのアクセス レベルが設定されるためです。</span><span class="sxs-lookup"><span data-stu-id="6676b-137">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
- <span data-ttu-id="6676b-138">**戻り値の型。**</span><span class="sxs-lookup"><span data-stu-id="6676b-138">**Return Type.**</span></span> <span data-ttu-id="6676b-139">[Property ステートメント](property-statement.md)では、それによって返される値のデータ型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="6676b-139">The [Property Statement](property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="6676b-140">`Get` プロシージャでは、そのデータ型が自動的に返されます。</span><span class="sxs-lookup"><span data-stu-id="6676b-140">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="6676b-141">任意のデータ型や、列挙、構造体、クラス、またはインターフェイスの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6676b-141">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="6676b-142">`Property` ステートメントで `returntype` を指定していない場合、プロシージャによって `Object` が返されます。</span><span class="sxs-lookup"><span data-stu-id="6676b-142">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="6676b-143">動作</span><span class="sxs-lookup"><span data-stu-id="6676b-143">Behavior</span></span>  
  
- <span data-ttu-id="6676b-144">**プロシージャからの復帰。**</span><span class="sxs-lookup"><span data-stu-id="6676b-144">**Returning from a Procedure.**</span></span> <span data-ttu-id="6676b-145">`Get` プロシージャから呼び出し元のコードに戻ると、そのプロパティ値を要求したステートメント内で実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="6676b-145">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="6676b-146">`Get` プロパティ プロシージャでは、[Return ステートメント](return-statement.md)を使用するか、プロパティ名に戻り値を代入することによって、値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="6676b-146">`Get` property procedures can return a value using either the [Return Statement](return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="6676b-147">詳細については、「[Function ステートメント](function-statement.md)」の "戻り値" に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6676b-147">For more information, see "Return Value" in [Function Statement](function-statement.md).</span></span>  
  
     <span data-ttu-id="6676b-148">`Exit Property` および `Return` ステートメントでは、プロパティ プロシージャがすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="6676b-148">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="6676b-149">任意の数の `Exit Property` および `Return` ステートメントをプロシージャ内の任意の場所に記述でき、`Exit Property` ステートメントと `Return` ステートメントを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="6676b-149">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
- <span data-ttu-id="6676b-150">**戻り値。**</span><span class="sxs-lookup"><span data-stu-id="6676b-150">**Return Value.**</span></span> <span data-ttu-id="6676b-151">`Get` プロシージャから値を返すには、プロパティ名に値を代入するか、[Return ステートメント](return-statement.md)に値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6676b-151">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](return-statement.md).</span></span> <span data-ttu-id="6676b-152">`Return` ステートメントでは、`Get` プロシージャに戻り値を代入すると同時に、プロシージャが終了します。</span><span class="sxs-lookup"><span data-stu-id="6676b-152">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="6676b-153">プロパティ名に値を代入せずに、`Exit Property` を使用すると、`Get` プロシージャからは、プロパティのデータ型の既定値が返されます。</span><span class="sxs-lookup"><span data-stu-id="6676b-153">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="6676b-154">詳細については、「[Function ステートメント](function-statement.md)」の "戻り値" に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6676b-154">For more information, see "Return Value" in [Function Statement](function-statement.md).</span></span>  
  
     <span data-ttu-id="6676b-155">次の例では、読み取り専用プロパティ `quoteForTheDay` で、プライベート変数 `quoteValue` に保持されている値を返すことができる 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6676b-155">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="6676b-156">例</span><span class="sxs-lookup"><span data-stu-id="6676b-156">Example</span></span>  
 <span data-ttu-id="6676b-157">次の例では、`Get` ステートメントを使用してプロパティの値を返しています。</span><span class="sxs-lookup"><span data-stu-id="6676b-157">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="6676b-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="6676b-158">See also</span></span>

- [<span data-ttu-id="6676b-159">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="6676b-159">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="6676b-160">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="6676b-160">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="6676b-161">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="6676b-161">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="6676b-162">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="6676b-162">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="6676b-163">チュートリアル: クラスの定義</span><span class="sxs-lookup"><span data-stu-id="6676b-163">Walkthrough: Defining Classes</span></span>](../../programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
