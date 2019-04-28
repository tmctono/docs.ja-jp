---
title: '方法: プロパティ (Visual Basic) を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: 91f34de36e88724ccab21097bf54a4604f7eee37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665781"
---
# <a name="how-to-create-a-property-visual-basic"></a><span data-ttu-id="544c5-102">方法: プロパティ (Visual Basic) を作成します。</span><span class="sxs-lookup"><span data-stu-id="544c5-102">How to: Create a Property (Visual Basic)</span></span>
<span data-ttu-id="544c5-103">プロパティの定義との間を囲む、`Property`ステートメントおよび`End Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="544c5-103">You enclose a property definition between a `Property` statement and an `End Property` statement.</span></span> <span data-ttu-id="544c5-104">この定義内で定義、 `Get` 、プロシージャ、`Set`プロシージャ、またはその両方です。</span><span class="sxs-lookup"><span data-stu-id="544c5-104">Within this definition you define a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="544c5-105">プロパティのすべてのコードが、これらのプロシージャ内に存在します。</span><span class="sxs-lookup"><span data-stu-id="544c5-105">All the property's code lies within these procedures.</span></span>  
  
 <span data-ttu-id="544c5-106">`Get`プロパティの値を取得し、`Set`プロシージャが値を格納します。</span><span class="sxs-lookup"><span data-stu-id="544c5-106">The `Get` procedure retrieves the property's value, and the `Set` procedure stores a value.</span></span> <span data-ttu-id="544c5-107">読み取り/書き込みアクセス権のプロパティを設定する場合、両方の手順を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="544c5-107">If you want the property to have read/write access, you must define both procedures.</span></span> <span data-ttu-id="544c5-108">読み取り専用プロパティを定義するのみ`Get`、書き込み専用プロパティで定義することのみ`Set`します。</span><span class="sxs-lookup"><span data-stu-id="544c5-108">For a read-only property, you define only `Get`, and for a write-only property, you define only `Set`.</span></span>  
  
### <a name="to-create-a-property"></a><span data-ttu-id="544c5-109">プロパティを作成するには</span><span class="sxs-lookup"><span data-stu-id="544c5-109">To create a property</span></span>  
  
1. <span data-ttu-id="544c5-110">任意のプロパティまたはプロシージャの外側を使用して、 [Property ステートメント](../../../../visual-basic/language-reference/statements/property-statement.md)、その後に、`End Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="544c5-110">Outside any property or procedure, use a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), followed by an `End Property` statement.</span></span>  
  
2. <span data-ttu-id="544c5-111">次のプロパティは、パラメーターを受け取る場合、`Property`パラメーター リストをかっこで、プロシージャの名前を持つキーワード。</span><span class="sxs-lookup"><span data-stu-id="544c5-111">If the property takes parameters, follow the `Property` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="544c5-112">かっこの後に、`As`プロパティの値のデータ型を指定する句。</span><span class="sxs-lookup"><span data-stu-id="544c5-112">Follow the parentheses with an `As` clause to specify the data type of the property's value.</span></span> <span data-ttu-id="544c5-113">書き込み専用プロパティの場合でもデータ型を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="544c5-113">You must specify the data type even for a write-only property.</span></span>  
  
4. <span data-ttu-id="544c5-114">追加`Get`と`Set`プロシージャに、必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="544c5-114">Add `Get` and `Set` procedures, as appropriate.</span></span> <span data-ttu-id="544c5-115">次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="544c5-115">See the following directions.</span></span>  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a><span data-ttu-id="544c5-116">プロパティの値を取得する Get プロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="544c5-116">To create a Get procedure that retrieves a property value</span></span>  
  
1. <span data-ttu-id="544c5-117">間、`Property`と`End Property`、ステートメントの記述、 [Get ステートメント](../../../../visual-basic/language-reference/statements/get-statement.md)、その後に、`End Get`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="544c5-117">Between the `Property` and `End Property` statements, write a [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md), followed by an `End Get` statement.</span></span> <span data-ttu-id="544c5-118">パラメーターを定義する必要はありません、`Get`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="544c5-118">You do not need to define any parameters for the `Get` procedure.</span></span>  
  
2. <span data-ttu-id="544c5-119">間で、プロパティの値を取得するコードのステートメントを配置、`Get`と`End Get`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="544c5-119">Place the code statements to retrieve the property's value between the `Get` and `End Get` statements.</span></span> <span data-ttu-id="544c5-120">その他の計算やデータ操作を生成して、プロパティの値を返すだけでなく、このコードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="544c5-120">This code can include other calculations and data manipulations in addition to generating and returning the property's value.</span></span>  
  
3. <span data-ttu-id="544c5-121">使用して、`Return`ステートメントを呼び出し元のコードに、プロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="544c5-121">Use a `Return` statement to return the property's value to the calling code.</span></span>  
  
 <span data-ttu-id="544c5-122">記述する必要があります、`Get`プロシージャおよび読み取り専用プロパティの読み取り/書き込みプロパティ。</span><span class="sxs-lookup"><span data-stu-id="544c5-122">You must write a `Get` procedure for a read-write property and for a read-only property.</span></span> <span data-ttu-id="544c5-123">定義する必要があります、`Get`書き込み専用プロパティ プロシージャをします。</span><span class="sxs-lookup"><span data-stu-id="544c5-123">You must not define a `Get` procedure for a write-only property.</span></span>  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a><span data-ttu-id="544c5-124">プロパティの値を書き込みます Set プロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="544c5-124">To create a Set procedure that writes a property's value</span></span>  
  
1. <span data-ttu-id="544c5-125">間、`Property`と`End Property`、ステートメントの記述、 [Set ステートメント](../../../../visual-basic/language-reference/statements/set-statement.md)、その後に、`End Set`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="544c5-125">Between the `Property` and `End Property` statements, write a [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md), followed by an `End Set` statement.</span></span>  
  
2. <span data-ttu-id="544c5-126">`Set`ステートメントでは、以下の`Set`パラメーター リストをかっこで囲まれたキーワード。</span><span class="sxs-lookup"><span data-stu-id="544c5-126">In the `Set` statement, follow the `Set` keyword with a parameter list in parentheses.</span></span> <span data-ttu-id="544c5-127">このパラメーターの一覧には、呼び出し元のコードに渡される値の少なくとも値パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="544c5-127">This parameter list must include at least a value parameter for the value passed by the calling code.</span></span> <span data-ttu-id="544c5-128">この値のパラメーターの既定の名前は`Value`、該当する場合は、別の名前を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="544c5-128">The default name for this value parameter is `Value`, but you can use a different name if appropriate.</span></span> <span data-ttu-id="544c5-129">データは、型、プロパティ自体と同じ値のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="544c5-129">The value parameter must have the same data type as the property itself.</span></span>  
  
3. <span data-ttu-id="544c5-130">間でプロパティに値を格納するコードのステートメントを配置、`Set`と`End Set`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="544c5-130">Place the code statements to store a value in the property between the `Set` and `End Set` statements.</span></span> <span data-ttu-id="544c5-131">このコードは、他の計算や検査して、プロパティの値を格納するだけでなくデータ操作を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="544c5-131">This code can include other calculations and data manipulations in addition to validating and storing the property's value.</span></span>  
  
4. <span data-ttu-id="544c5-132">値パラメーターを使用して、呼び出し元のコードによって提供される値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="544c5-132">Use the value parameter to accept the value supplied by the calling code.</span></span> <span data-ttu-id="544c5-133">この値は、代入ステートメントに直接格納するかを格納する内部値を計算する式で使用します。</span><span class="sxs-lookup"><span data-stu-id="544c5-133">You can either store this value directly in an assignment statement, or use it in an expression to calculate the internal value to be stored.</span></span>  
  
 <span data-ttu-id="544c5-134">記述する必要があります、`Set`プロシージャの読み取り/書き込みプロパティおよび書き込み専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="544c5-134">You must write a `Set` procedure for a read-write property and for a write-only property.</span></span> <span data-ttu-id="544c5-135">定義する必要があります、`Set`読み取り専用プロパティ プロシージャをします。</span><span class="sxs-lookup"><span data-stu-id="544c5-135">You must not define a `Set` procedure for a read-only property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="544c5-136">例</span><span class="sxs-lookup"><span data-stu-id="544c5-136">Example</span></span>  
 <span data-ttu-id="544c5-137">次の例では、2 つの構成名、名、および、最後の名前と完全な名前を格納する読み取り/書き込みプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="544c5-137">The following example creates a read/write property that stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="544c5-138">呼び出し元のコードを読み取るとき`fullName`、`Get`プロシージャは、2 つの構成名を結合し、完全な名前を返します。</span><span class="sxs-lookup"><span data-stu-id="544c5-138">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="544c5-139">呼び出し元のコードによって、新しい完全な名前を割り当てられるとき、`Set`プロシージャは、それを 2 つの部分に分割しようと試みます。</span><span class="sxs-lookup"><span data-stu-id="544c5-139">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="544c5-140">場所が見つからない場合すべて最初の名前として格納します。</span><span class="sxs-lookup"><span data-stu-id="544c5-140">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 <span data-ttu-id="544c5-141">次の例では、一般的なプロパティ プロシージャの呼び出し`fullName`します。</span><span class="sxs-lookup"><span data-stu-id="544c5-141">The following example shows typical calls to the property procedures of `fullName`.</span></span> <span data-ttu-id="544c5-142">最初の呼び出しは、プロパティの値を設定し、2 番目の呼び出しでは、それを取得します。</span><span class="sxs-lookup"><span data-stu-id="544c5-142">The first call sets the property value and the second call retrieves it.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="544c5-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="544c5-143">See also</span></span>

- [<span data-ttu-id="544c5-144">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="544c5-144">Procedures</span></span>](./index.md)
- [<span data-ttu-id="544c5-145">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="544c5-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="544c5-146">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="544c5-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="544c5-147">Visual Basic でのプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="544c5-147">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="544c5-148">方法: 混合アクセス レベルを持つプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="544c5-148">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="544c5-149">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="544c5-149">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="544c5-150">方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="544c5-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="544c5-151">方法: プロパティに値を格納します。</span><span class="sxs-lookup"><span data-stu-id="544c5-151">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="544c5-152">方法: プロパティから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="544c5-152">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
