---
title: '方法 : プロパティに値を格納する'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: ad0d0e81f94dd3dead50f21c3bd6ff580c004dd6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346054"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="6a111-102">方法: プロパティに値を格納する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a111-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="6a111-103">プロパティに値を格納するには、プロパティ名を代入ステートメントの左側に配置します。</span><span class="sxs-lookup"><span data-stu-id="6a111-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="6a111-104">プロパティの `Set` プロシージャには値が格納されますが、名前で明示的に呼び出すことはありません。</span><span class="sxs-lookup"><span data-stu-id="6a111-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="6a111-105">変数を使用する場合と同じように、プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a111-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="6a111-106">Visual Basic によって、プロパティのプロシージャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6a111-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="6a111-107">プロパティに値を格納するには</span><span class="sxs-lookup"><span data-stu-id="6a111-107">To store a value in a property</span></span>  
  
1. <span data-ttu-id="6a111-108">代入ステートメントの左側にあるプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a111-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="6a111-109">次の例では、Visual Basic `TimeOfDay` プロパティの値を正午に設定し、その `Set` プロシージャを暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6a111-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="6a111-110">プロパティが引数を受け取る場合は、プロパティ名の後にかっこを付けて引数リストを囲みます。</span><span class="sxs-lookup"><span data-stu-id="6a111-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="6a111-111">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="6a111-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="6a111-112">引数リストに引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="6a111-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="6a111-113">引数は、プロパティが対応するパラメーターを定義する順序と同じ順序で指定してください。</span><span class="sxs-lookup"><span data-stu-id="6a111-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4. <span data-ttu-id="6a111-114">代入ステートメントの右辺に生成される値は、プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6a111-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a111-115">参照</span><span class="sxs-lookup"><span data-stu-id="6a111-115">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="6a111-116">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="6a111-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="6a111-117">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="6a111-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6a111-118">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="6a111-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="6a111-119">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="6a111-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="6a111-120">方法 : プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="6a111-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="6a111-121">方法 : 複数のアクセス レベルを持つプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="6a111-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="6a111-122">方法 : プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="6a111-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="6a111-123">方法: Visual Basic で既定のプロパティを宣言して呼び出す</span><span class="sxs-lookup"><span data-stu-id="6a111-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="6a111-124">方法 : プロパティから値を取得する</span><span class="sxs-lookup"><span data-stu-id="6a111-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
