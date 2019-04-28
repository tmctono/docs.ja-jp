---
title: Set ステートメント (Visual Basic)
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
ms.openlocfilehash: 0a8d95ffbabf03a0e6c9d88edb28c248b60f3252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783878"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="9f1a2-102">Set ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f1a2-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="9f1a2-103">宣言を`Set`プロパティ プロシージャのプロパティに値を代入するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f1a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f1a2-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="9f1a2-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9f1a2-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="9f1a2-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-106">Optional.</span></span> <span data-ttu-id="9f1a2-107">参照してください[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="9f1a2-108">1 つだけでは省略可能、`Get`と`Set`このプロパティ内のステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="9f1a2-109">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="9f1a2-110">Protected</span><span class="sxs-lookup"><span data-stu-id="9f1a2-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [<span data-ttu-id="9f1a2-111">Friend</span><span class="sxs-lookup"><span data-stu-id="9f1a2-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [<span data-ttu-id="9f1a2-112">Private</span><span class="sxs-lookup"><span data-stu-id="9f1a2-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="9f1a2-113">「 [Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="9f1a2-114">必須。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-114">Required.</span></span> <span data-ttu-id="9f1a2-115">プロパティの新しい値を含むパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="9f1a2-116">場合に、必ず`Option Strict`は`On`します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="9f1a2-117">データ型、`value`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="9f1a2-118">指定されたデータ型は、プロパティのデータ型と同じである必要があります、これ`Set`ステートメントが宣言されます。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="9f1a2-119">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-119">Optional.</span></span> <span data-ttu-id="9f1a2-120">場合に実行する 1 つまたは複数のステートメント、`Set`プロパティ プロシージャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="9f1a2-121">必須。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-121">Required.</span></span> <span data-ttu-id="9f1a2-122">定義を終了、`Set`プロパティ プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f1a2-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f1a2-123">Remarks</span></span>  
 <span data-ttu-id="9f1a2-124">すべてのプロパティがあります、`Set`プロパティ プロシージャ、プロパティが指定されていない限り`ReadOnly`します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="9f1a2-125">`Set`プロパティの値を設定する手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="9f1a2-126">Visual Basic がプロパティを自動的に呼び出します`Set`手順、代入ステートメントは、プロパティに格納される値を提供する場合。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="9f1a2-127">Visual Basic のパラメーターを渡す、`Set`プロパティ割り当て中にプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="9f1a2-128">パラメーターを指定しない場合`Set`、統合開発環境 (IDE) という名前の暗黙のパラメーターを使用して`value`します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="9f1a2-129">パラメーターは、プロパティに割り当てられる値を保持します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="9f1a2-130">通常プライベート ローカル変数にこの値を格納して返すたびに、`Get`プロシージャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="9f1a2-131">プロパティ宣言の本体でのみ、プロパティを含めることができます`Get`と`Set`間で、プロシージャ、 [Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)と`End Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="9f1a2-132">これらのプロシージャ以外のものを格納できません。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="9f1a2-133">具体的には、プロパティの現在の値を格納できません。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="9f1a2-134">に、プロパティ プロシージャのいずれかの内部で保存する場合、その他のプロパティ プロシージャ アクセスできないために、プロパティの外部には、この値を格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="9f1a2-135">値を格納する通常の方法も、[プライベート](../../../visual-basic/language-reference/modifiers/private.md)プロパティと同じレベルで宣言された変数。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="9f1a2-136">定義する必要があります、`Set`適用されるプロパティ内のプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="9f1a2-137">`Set`プロシージャの既定値はその包含するプロパティのアクセス レベルを使用しない限り`accessmodifier`で、`Set`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9f1a2-138">ルール</span><span class="sxs-lookup"><span data-stu-id="9f1a2-138">Rules</span></span>  
  
- <span data-ttu-id="9f1a2-139">**混合アクセス レベル。**</span><span class="sxs-lookup"><span data-stu-id="9f1a2-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="9f1a2-140">必要に応じていずれかの異なるアクセス レベルを指定することができます、読み取り/書き込みプロパティを定義する場合、`Get`または`Set`両方ではなく、プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="9f1a2-141">これを行うと、プロシージャのアクセス レベル、プロパティのアクセス レベルよりもより制限の厳しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="9f1a2-142">例では、プロパティが宣言されている場合、 `Friend`、宣言することができます、`Set`プロシージャ`Private`、なく`Public`します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="9f1a2-143">定義する場合、`WriteOnly`プロパティ、`Set`プロシージャは、全体のプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="9f1a2-144">レベル別のアクセスを宣言することはできません`Set`プロパティの 2 つのアクセス レベルを設定することがあるため、します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="9f1a2-145">動作</span><span class="sxs-lookup"><span data-stu-id="9f1a2-145">Behavior</span></span>  
  
- <span data-ttu-id="9f1a2-146">**プロパティ プロシージャから取得します。**</span><span class="sxs-lookup"><span data-stu-id="9f1a2-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="9f1a2-147">ときに、`Set`実行はプロシージャは、呼び出し元のコードに返す、次の格納される値を提供するステートメントが続行されます。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="9f1a2-148">`Set` プロパティ プロシージャは、いずれかを使用して返すことができます、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)または[Exit ステートメント](../../../visual-basic/language-reference/statements/exit-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="9f1a2-149">`Exit Property`と`Return`ステートメントでは、プロパティ プロシージャからすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="9f1a2-150">任意の数の`Exit Property`と`Return`ステートメントは、手順では、どこでも表示でき、組み合わせることができます`Exit Property`と`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f1a2-151">例</span><span class="sxs-lookup"><span data-stu-id="9f1a2-151">Example</span></span>  
 <span data-ttu-id="9f1a2-152">次の例では、`Set`プロパティの値を設定するステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f1a2-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="9f1a2-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f1a2-153">See also</span></span>

- [<span data-ttu-id="9f1a2-154">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="9f1a2-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="9f1a2-155">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="9f1a2-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="9f1a2-156">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="9f1a2-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="9f1a2-157">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="9f1a2-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
