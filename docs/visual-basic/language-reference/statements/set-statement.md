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
ms.openlocfilehash: 75ad6d87f1785fea13a282d953f117c9c234e203
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349566"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="c51c6-102">Set ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c51c6-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="c51c6-103">プロパティに値を割り当てるために使用される `Set` プロパティプロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c51c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="c51c6-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="c51c6-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="c51c6-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="c51c6-106">省略可。</span><span class="sxs-lookup"><span data-stu-id="c51c6-106">Optional.</span></span> <span data-ttu-id="c51c6-107">「[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c51c6-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="c51c6-108">このプロパティの `Get` および `Set` ステートメントのうちの1つで、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c51c6-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="c51c6-109">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="c51c6-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="c51c6-110">Protected</span><span class="sxs-lookup"><span data-stu-id="c51c6-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [<span data-ttu-id="c51c6-111">Friend</span><span class="sxs-lookup"><span data-stu-id="c51c6-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [<span data-ttu-id="c51c6-112">Private</span><span class="sxs-lookup"><span data-stu-id="c51c6-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="c51c6-113">「[Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c51c6-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="c51c6-114">必須。</span><span class="sxs-lookup"><span data-stu-id="c51c6-114">Required.</span></span> <span data-ttu-id="c51c6-115">プロパティの新しい値を格納しているパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c51c6-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="c51c6-116">`Option Strict` が `On`の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="c51c6-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="c51c6-117">`value` パラメーターのデータ型。</span><span class="sxs-lookup"><span data-stu-id="c51c6-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="c51c6-118">指定するデータ型は、この `Set` ステートメントが宣言されているプロパティのデータ型と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51c6-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="c51c6-119">省略可。</span><span class="sxs-lookup"><span data-stu-id="c51c6-119">Optional.</span></span> <span data-ttu-id="c51c6-120">`Set` プロパティプロシージャが呼び出されたときに実行される1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="c51c6-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="c51c6-121">必須。</span><span class="sxs-lookup"><span data-stu-id="c51c6-121">Required.</span></span> <span data-ttu-id="c51c6-122">`Set` property プロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c51c6-123">コメント</span><span class="sxs-lookup"><span data-stu-id="c51c6-123">Remarks</span></span>  
 <span data-ttu-id="c51c6-124">プロパティが `ReadOnly`としてマークされている場合を除き、すべてのプロパティには `Set` プロパティプロシージャが必要です。</span><span class="sxs-lookup"><span data-stu-id="c51c6-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="c51c6-125">`Set` プロシージャは、プロパティの値を設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c51c6-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="c51c6-126">Visual Basic は、プロパティに格納される値が代入ステートメントによって提供されるときに、プロパティの `Set` プロシージャを自動的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="c51c6-127">Visual Basic は、プロパティの割り当て時に `Set` プロシージャにパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="c51c6-128">`Set`のパラメーターを指定しない場合、統合開発環境 (IDE) は `value`という名前の暗黙的なパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="c51c6-129">パラメーターは、プロパティに割り当てられる値を保持します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="c51c6-130">通常、この値はプライベートローカル変数に格納し、`Get` プロシージャが呼び出されるたびに返されます。</span><span class="sxs-lookup"><span data-stu-id="c51c6-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="c51c6-131">プロパティ宣言の本体には、プロパティの `Get` と、[プロパティステートメント](../../../visual-basic/language-reference/statements/property-statement.md)と `End Property` ステートメントの間の `Set` プロシージャのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c51c6-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="c51c6-132">これらのプロシージャ以外を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="c51c6-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="c51c6-133">特に、プロパティの現在の値を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="c51c6-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="c51c6-134">この値はプロパティの外部に格納する必要があります。これは、プロパティプロシージャの内部に格納する場合、他のプロパティプロシージャがアクセスできないためです。</span><span class="sxs-lookup"><span data-stu-id="c51c6-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="c51c6-135">通常の方法では、プロパティと同じレベルで宣言された[プライベート](../../../visual-basic/language-reference/modifiers/private.md)変数に値を格納します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="c51c6-136">`Set` プロシージャは、適用先のプロパティ内で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51c6-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="c51c6-137">`Set` ステートメントで `accessmodifier` を使用しない限り、`Set` プロシージャの既定値は、それを含むプロパティのアクセスレベルです。</span><span class="sxs-lookup"><span data-stu-id="c51c6-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c51c6-138">ルール</span><span class="sxs-lookup"><span data-stu-id="c51c6-138">Rules</span></span>  
  
- <span data-ttu-id="c51c6-139">**混合アクセスレベル。**</span><span class="sxs-lookup"><span data-stu-id="c51c6-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="c51c6-140">読み取り/書き込みプロパティを定義する場合は、必要に応じて、`Get` または `Set` のいずれかのプロシージャに対して異なるアクセスレベルを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c51c6-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="c51c6-141">この場合、プロシージャのアクセスレベルは、プロパティのアクセスレベルよりも制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51c6-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="c51c6-142">たとえば、プロパティが `Friend`として宣言されている場合は、`Set` プロシージャ `Private`を宣言できますが、`Public`は宣言できません。</span><span class="sxs-lookup"><span data-stu-id="c51c6-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="c51c6-143">`WriteOnly` プロパティを定義する場合、`Set` プロシージャはプロパティ全体を表します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="c51c6-144">`Set`に対して異なるアクセスレベルを宣言することはできません。これは、プロパティに2つのアクセスレベルが設定されるためです。</span><span class="sxs-lookup"><span data-stu-id="c51c6-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c51c6-145">動作</span><span class="sxs-lookup"><span data-stu-id="c51c6-145">Behavior</span></span>  
  
- <span data-ttu-id="c51c6-146">**プロパティプロシージャからを返します。**</span><span class="sxs-lookup"><span data-stu-id="c51c6-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="c51c6-147">`Set` プロシージャが呼び出し元のコードに戻ると、格納される値が指定されたステートメントの後で実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="c51c6-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="c51c6-148">`Set` プロパティプロシージャは、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)または[Exit ステートメント](../../../visual-basic/language-reference/statements/exit-statement.md)のいずれかを使用してを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="c51c6-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="c51c6-149">`Exit Property` ステートメントおよび `Return` ステートメントでは、プロパティプロシージャがすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="c51c6-150">プロシージャ内の任意の場所で任意の数の `Exit Property` および `Return` ステートメントを使用できます。また、`Exit Property` と `Return` のステートメントを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="c51c6-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c51c6-151">例</span><span class="sxs-lookup"><span data-stu-id="c51c6-151">Example</span></span>  
 <span data-ttu-id="c51c6-152">次の例では、`Set` ステートメントを使用して、プロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c51c6-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="c51c6-153">参照</span><span class="sxs-lookup"><span data-stu-id="c51c6-153">See also</span></span>

- [<span data-ttu-id="c51c6-154">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="c51c6-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="c51c6-155">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="c51c6-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="c51c6-156">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="c51c6-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="c51c6-157">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c51c6-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
