---
title: オブジェクトの型の決定
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: a77cc0603a0b61f58a4aa703c4b1e6ef4c26729c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345199"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="2b298-102">オブジェクトの型の決定 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b298-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="2b298-103">汎用オブジェクト変数 (`Object` として宣言する変数) では、あらゆるクラスのオブジェクトを保持できます。</span><span class="sxs-lookup"><span data-stu-id="2b298-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="2b298-104">`Object` 型の変数を使用する場合、オブジェクトのクラスによって異なるアクションを実行しなければならないことがあります。たとえば、オブジェクトによっては、特定のプロパティやメソッドがサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2b298-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="2b298-105">Visual Basic では、`TypeName` 関数と `TypeOf...Is` 演算子という 2 つの方法によって、オブジェクト変数に格納されているオブジェクトの型を特定できます。</span><span class="sxs-lookup"><span data-stu-id="2b298-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="2b298-106">TypeName と TypeOf…Is</span><span class="sxs-lookup"><span data-stu-id="2b298-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="2b298-107">`TypeName` 関数の戻り値は文字列であり、次のコードで示すように、オブジェクトのクラス名を格納または表示する必要がある場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="2b298-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="2b298-108">`TypeOf...Is` 演算子は、`TypeName` を使用した同等の文字列比較よりもはるかに高速であるため、オブジェクトの型のテストに最も適しています。</span><span class="sxs-lookup"><span data-stu-id="2b298-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="2b298-109">次のコードでは、`If...Then...Else` ステートメント内で `TypeOf...Is` を使用しています。</span><span class="sxs-lookup"><span data-stu-id="2b298-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="2b298-110">ここで注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="2b298-110">A word of caution is due here.</span></span> <span data-ttu-id="2b298-111">オブジェクトが特定の型であるか、または特定の型から派生している場合、`TypeOf...Is` 演算子は `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="2b298-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="2b298-112">Visual Basic で行うほとんどすべての操作にはオブジェクトが関係しています。これには、文字列や整数など、オブジェクトとは通常見なされない要素も含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b298-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="2b298-113">こうしたオブジェクトは、<xref:System.Object> から派生し、そのメソッドを継承しています。</span><span class="sxs-lookup"><span data-stu-id="2b298-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="2b298-114">`TypeOf...Is` 演算子に `Integer` を渡して、`Object` かどうかを評価した場合、`True` が返されます。</span><span class="sxs-lookup"><span data-stu-id="2b298-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="2b298-115">次の例では、パラメーター `InParam` は `Object` であり、かつ `Integer` でもあると返されます。</span><span class="sxs-lookup"><span data-stu-id="2b298-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="2b298-116">次の例では、`TypeOf...Is` と `TypeName` の両方を使用して、`Ctrl` 引数から渡されたオブジェクトの型を特定します。</span><span class="sxs-lookup"><span data-stu-id="2b298-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="2b298-117">`TestObject` プロシージャにより、3 種類のコントロールを使用して `ShowType` を呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="2b298-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="2b298-118">例を実行するには</span><span class="sxs-lookup"><span data-stu-id="2b298-118">To run the example</span></span>  
  
1. <span data-ttu-id="2b298-119">新しい Windows アプリケーション プロジェクトを作成して、フォームに <xref:System.Windows.Forms.Button> コントロール、<xref:System.Windows.Forms.CheckBox> コントロール、および <xref:System.Windows.Forms.RadioButton> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b298-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2. <span data-ttu-id="2b298-120">フォームのボタンで `TestObject` プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2b298-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3. <span data-ttu-id="2b298-121">次のコードをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="2b298-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="2b298-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b298-122">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="2b298-123">文字列名によるプロパティまたはメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="2b298-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="2b298-124">Object 型</span><span class="sxs-lookup"><span data-stu-id="2b298-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="2b298-125">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="2b298-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="2b298-126">String データ型</span><span class="sxs-lookup"><span data-stu-id="2b298-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="2b298-127">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="2b298-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
