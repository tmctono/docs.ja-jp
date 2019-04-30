---
title: オブジェクトの型の決定 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 4014bef2e0c27a0f6a684bc1ed95019f392062a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050520"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="5055e-102">オブジェクトの型の決定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5055e-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="5055e-103">汎用オブジェクト変数 (つまり、変数として宣言する`Object`) 任意のクラスからオブジェクトを保持できます。</span><span class="sxs-lookup"><span data-stu-id="5055e-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="5055e-104">型の変数を使用する場合`Object`オブジェクトのクラスに基づいて異なるアクションを実行する必要があります。 たとえば、一部のオブジェクト可能性がありますサポートしていませんが特定のプロパティまたはメソッドです。</span><span class="sxs-lookup"><span data-stu-id="5055e-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="5055e-105">Visual Basic のオブジェクト変数に保存するオブジェクトの種類を決定する 2 つの手段を提供します。、`TypeName`関数と`TypeOf...Is`演算子。</span><span class="sxs-lookup"><span data-stu-id="5055e-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="5055e-106">TypeName と TypeOf...Is</span><span class="sxs-lookup"><span data-stu-id="5055e-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="5055e-107">`TypeName`関数は、文字列が返され、最適な選択肢は、次のコード フラグメントで示すように、格納したり、オブジェクトのクラス名を表示する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="5055e-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="5055e-108">`TypeOf...Is`演算子には、等価の文字列比較が使用するよりもはるかに高速であるために、オブジェクトの型をテストするための最適な選択肢`TypeName`します。</span><span class="sxs-lookup"><span data-stu-id="5055e-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="5055e-109">次のコード フラグメントを使用して`TypeOf...Is`内、`If...Then...Else`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="5055e-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="5055e-110">注意事項は、ここで期限。</span><span class="sxs-lookup"><span data-stu-id="5055e-110">A word of caution is due here.</span></span> <span data-ttu-id="5055e-111">`TypeOf...Is`演算子を返します`True`オブジェクトが特定の種類のかが特定の型から派生します。</span><span class="sxs-lookup"><span data-stu-id="5055e-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="5055e-112">Visual Basic で行うほぼすべてには、オブジェクトで、文字列や整数などのオブジェクトとして考えることは、通常、いくつかの要素を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5055e-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="5055e-113">これらのオブジェクトから派生するためのメソッドを継承<xref:System.Object>します。</span><span class="sxs-lookup"><span data-stu-id="5055e-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="5055e-114">渡されたときに、`Integer`を評価および`Object`、`TypeOf...Is`演算子を返します`True`します。</span><span class="sxs-lookup"><span data-stu-id="5055e-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="5055e-115">次の例で提供されるレポート パラメーター`InParam`はどちらも、`Object`と`Integer`:</span><span class="sxs-lookup"><span data-stu-id="5055e-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="5055e-116">次の例では、両方は使用して`TypeOf...Is`と`TypeName`内で渡されるオブジェクトの種類を決定する、`Ctrl`引数。</span><span class="sxs-lookup"><span data-stu-id="5055e-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="5055e-117">`TestObject`プロシージャ呼び出し`ShowType`で 3 つの異なる種類のコントロール。</span><span class="sxs-lookup"><span data-stu-id="5055e-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="5055e-118">例を実行するには</span><span class="sxs-lookup"><span data-stu-id="5055e-118">To run the example</span></span>  
  
1. <span data-ttu-id="5055e-119">新しい Windows アプリケーション プロジェクトを作成し、追加、<xref:System.Windows.Forms.Button>コントロール、<xref:System.Windows.Forms.CheckBox>コントロール、および<xref:System.Windows.Forms.RadioButton>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="5055e-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2. <span data-ttu-id="5055e-120">フォーム上のボタンから呼び出して、`TestObject`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="5055e-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3. <span data-ttu-id="5055e-121">次のコードをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="5055e-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="5055e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5055e-122">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="5055e-123">文字列名によるプロパティまたはメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="5055e-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="5055e-124">Object 型</span><span class="sxs-lookup"><span data-stu-id="5055e-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="5055e-125">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="5055e-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="5055e-126">String データ型</span><span class="sxs-lookup"><span data-stu-id="5055e-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="5055e-127">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="5055e-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
