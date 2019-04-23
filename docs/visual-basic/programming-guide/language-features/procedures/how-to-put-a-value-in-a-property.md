---
title: '方法: プロパティ (Visual Basic) で、値を入力します。'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: e6aee5ea36c0315d5b01ae2734d17c9e7dab8e93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341856"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="88332-102">方法: プロパティ (Visual Basic) で、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="88332-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="88332-103">プロパティに値を格納するには、代入ステートメントの左側にあるプロパティ名を置きます。</span><span class="sxs-lookup"><span data-stu-id="88332-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="88332-104">プロパティの`Set`プロシージャに、値が格納されますが、明示的に呼び出さない場合、名前でします。</span><span class="sxs-lookup"><span data-stu-id="88332-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="88332-105">変数を使用する場合と同様に、プロパティを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="88332-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="88332-106">Visual Basic では、プロパティのプロシージャ呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="88332-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="88332-107">プロパティに値を格納するには</span><span class="sxs-lookup"><span data-stu-id="88332-107">To store a value in a property</span></span>  
  
1. <span data-ttu-id="88332-108">代入ステートメントの左側にあるプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="88332-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="88332-109">次の例では、Visual Basic の値を設定する`TimeOfDay`プロパティ、正午を暗黙的に呼び出して、`Set`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="88332-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="88332-110">プロパティが引数を受け取る場合は、次の引数リストを囲むためにかっこによるプロパティ名。</span><span class="sxs-lookup"><span data-stu-id="88332-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="88332-111">引数がない場合、かっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="88332-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="88332-112">コンマで区切り、かっこ内の引数リストで、引数を配置します。</span><span class="sxs-lookup"><span data-stu-id="88332-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="88332-113">プロパティが、対応するパラメーターを定義するのと同じ順序で引数を指定してください。</span><span class="sxs-lookup"><span data-stu-id="88332-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4. <span data-ttu-id="88332-114">代入ステートメントの右側にある生成された値は、プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="88332-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88332-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="88332-115">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="88332-116">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="88332-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="88332-117">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="88332-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="88332-118">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="88332-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="88332-119">Visual Basic でのプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="88332-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="88332-120">方法: プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="88332-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="88332-121">方法: 混合アクセス レベルを持つプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="88332-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="88332-122">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="88332-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="88332-123">方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="88332-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="88332-124">方法: プロパティから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="88332-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
