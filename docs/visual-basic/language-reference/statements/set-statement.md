---
title: Set ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: 49d4c36805b64d7232a94e818256723a0437b6ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404188"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="97412-102">Set ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97412-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="97412-103">値をプロパティに割り当てるのに使用する `Set` プロパティ プロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="97412-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97412-104">構文</span><span class="sxs-lookup"><span data-stu-id="97412-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="97412-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="97412-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="97412-106">任意。</span><span class="sxs-lookup"><span data-stu-id="97412-106">Optional.</span></span> <span data-ttu-id="97412-107">「[属性リスト](attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97412-107">See [Attribute List](attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="97412-108">このプロパティの `Get` および `Set` ステートメントのいずれかで、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="97412-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="97412-109">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="97412-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="97412-110">Protected</span><span class="sxs-lookup"><span data-stu-id="97412-110">Protected</span></span>](../modifiers/protected.md)  
  
- [<span data-ttu-id="97412-111">Friend</span><span class="sxs-lookup"><span data-stu-id="97412-111">Friend</span></span>](../modifiers/friend.md)  
  
- [<span data-ttu-id="97412-112">Private</span><span class="sxs-lookup"><span data-stu-id="97412-112">Private</span></span>](../modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="97412-113">「 [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97412-113">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="97412-114">必須です。</span><span class="sxs-lookup"><span data-stu-id="97412-114">Required.</span></span> <span data-ttu-id="97412-115">プロパティの新しい値を含むパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="97412-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="97412-116">`Option Strict` が `On` の場合は必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="97412-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="97412-117">`value` パラメーターのデータ型。</span><span class="sxs-lookup"><span data-stu-id="97412-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="97412-118">指定するデータ型は、この `Set` ステートメントが宣言されているプロパティのデータ型と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="97412-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="97412-119">任意。</span><span class="sxs-lookup"><span data-stu-id="97412-119">Optional.</span></span> <span data-ttu-id="97412-120">`Set` プロパティ プロシージャが呼び出されたときに実行される 1 つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="97412-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="97412-121">必須です。</span><span class="sxs-lookup"><span data-stu-id="97412-121">Required.</span></span> <span data-ttu-id="97412-122">`Set` プロパティ プロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="97412-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97412-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="97412-123">Remarks</span></span>  
 <span data-ttu-id="97412-124">プロパティが `ReadOnly` とマークされている場合を除き、すべてのプロパティには `Set` プロパティ プロシージャが必要です。</span><span class="sxs-lookup"><span data-stu-id="97412-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="97412-125">`Set` プロシージャは、プロパティの値を設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="97412-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="97412-126">Visual Basic は、プロパティに格納される値が代入ステートメントによって提供されるときに、プロパティの `Set` プロシージャを自動的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="97412-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="97412-127">Visual Basic は、プロパティの割り当て時に `Set` プロシージャにパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="97412-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="97412-128">`Set` のパラメーターを指定しない場合、統合開発環境 (IDE) では `value` という名前の暗黙的なパラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="97412-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="97412-129">このパラメーターは、プロパティに割り当てられる値を保持します。</span><span class="sxs-lookup"><span data-stu-id="97412-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="97412-130">通常はこの値をプライベート ローカル変数に格納し、これは `Get` プロシージャが呼び出されるたびに返されます。</span><span class="sxs-lookup"><span data-stu-id="97412-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="97412-131">プロパティ宣言の本体には、[Property ステートメント](property-statement.md)と `End Property` ステートメントの間に、プロパティの `Get` と `Set` のプロシージャのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="97412-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="97412-132">これらのプロシージャ以外のものを格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="97412-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="97412-133">特に、プロパティの現在の値を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="97412-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="97412-134">この値は、プロパティの外部に格納する必要があります。それをいずれかのプロパティ プロシージャの内部に格納した場合、他のプロパティ プロシージャからアクセスできなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="97412-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="97412-135">通常の方法は、プロパティと同じレベルで宣言された [Private](../modifiers/private.md) 変数に値を格納することです。</span><span class="sxs-lookup"><span data-stu-id="97412-135">The usual approach is to store the value in a [Private](../modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="97412-136">`Set` プロシージャは、適用先のプロパティの内部で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97412-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="97412-137">`Set` ステートメントで `accessmodifier` を使用しない限り、`Set` プロシージャは既定で、それを含んでいるプロパティのアクセス レベルに設定されます。</span><span class="sxs-lookup"><span data-stu-id="97412-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="97412-138">ルール</span><span class="sxs-lookup"><span data-stu-id="97412-138">Rules</span></span>  
  
- <span data-ttu-id="97412-139">**混合アクセス レベル。**</span><span class="sxs-lookup"><span data-stu-id="97412-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="97412-140">読み取り/書き込みプロパティを定義する場合は、必要に応じて、`Get` または `Set` のいずれかのプロシージャに対して異なるアクセス レベルを指定できますが、両方に対して指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="97412-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="97412-141">この場合、プロシージャのアクセス レベルは、プロパティのアクセス レベルよりも制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97412-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="97412-142">たとえば、プロパティが `Friend` として宣言されている場合は、`Set` プロシージャを、`Public` ではなく `Private` として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="97412-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="97412-143">`WriteOnly` プロパティを定義する場合、`Set` プロシージャはプロパティ全体を表します。</span><span class="sxs-lookup"><span data-stu-id="97412-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="97412-144">`Set` に対して異なるアクセス レベルを宣言することはできません。それによって、プロパティに 2 つのアクセス レベルが設定されるためです。</span><span class="sxs-lookup"><span data-stu-id="97412-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="97412-145">動作</span><span class="sxs-lookup"><span data-stu-id="97412-145">Behavior</span></span>  
  
- <span data-ttu-id="97412-146">**プロパティ プロシージャからの復帰。**</span><span class="sxs-lookup"><span data-stu-id="97412-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="97412-147">`Set` プロシージャから呼び出し元のコードに返されると、実行は、格納される値を指定したステートメントの後のステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="97412-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="97412-148">`Set` プロパティ プロシージャは、[Return ステートメント](return-statement.md)または [Exit ステートメント](exit-statement.md)のいずれかを使用して返すことができます。</span><span class="sxs-lookup"><span data-stu-id="97412-148">`Set` property procedures can return using either the [Return Statement](return-statement.md) or the [Exit Statement](exit-statement.md).</span></span>  
  
     <span data-ttu-id="97412-149">`Exit Property` および `Return` ステートメントでは、プロパティ プロシージャがすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="97412-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="97412-150">任意の数の `Exit Property` および `Return` ステートメントをプロシージャ内の任意の場所に記述でき、`Exit Property` ステートメントと `Return` ステートメントを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="97412-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97412-151">例</span><span class="sxs-lookup"><span data-stu-id="97412-151">Example</span></span>  
 <span data-ttu-id="97412-152">次の例では、`Set` ステートメントを使用してプロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="97412-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="97412-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="97412-153">See also</span></span>

- [<span data-ttu-id="97412-154">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="97412-154">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="97412-155">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="97412-155">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="97412-156">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="97412-156">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="97412-157">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="97412-157">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
