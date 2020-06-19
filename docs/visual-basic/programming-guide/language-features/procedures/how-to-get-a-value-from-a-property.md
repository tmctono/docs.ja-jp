---
title: '方法: プロパティから値を取得する'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 2c92cd4a869acbb7c8c52fbf4117112967386498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387895"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="17eb9-102">方法: プロパティから値を取得する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17eb9-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="17eb9-103">プロパティの値を取得するには、プロパティ名を式に含めます。</span><span class="sxs-lookup"><span data-stu-id="17eb9-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="17eb9-104">プロパティの `Get` プロシージャによって値が取得されますが、名前で明示的に呼び出すことはありません。</span><span class="sxs-lookup"><span data-stu-id="17eb9-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="17eb9-105">変数を使用する場合と同様に、プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="17eb9-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="17eb9-106">Visual Basic によってプロパティのプロシージャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="17eb9-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="17eb9-107">プロパティから値を取得するには</span><span class="sxs-lookup"><span data-stu-id="17eb9-107">To retrieve a value from a property</span></span>  
  
1. <span data-ttu-id="17eb9-108">式内のプロパティ名は、変数名を使用する場合と同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="17eb9-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="17eb9-109">変数または定数を使用できる場所であればどこでもプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="17eb9-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="17eb9-110">\- または -</span><span class="sxs-lookup"><span data-stu-id="17eb9-110">-or-</span></span>  
  
     <span data-ttu-id="17eb9-111">代入ステートメント内で等号 (`=`) の後にプロパティ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="17eb9-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="17eb9-112">次の例では、Visual Basic `Now` プロパティの値を読み取り、その `Get` プロシージャを暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="17eb9-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="17eb9-113">プロパティが引数を受け取る場合は、プロパティ名の後にかっこで囲んだ引数リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="17eb9-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="17eb9-114">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="17eb9-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="17eb9-115">引数リストの引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="17eb9-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="17eb9-116">プロパティで定義されている対応するパラメーターと同じ順序で引数を指定してください。</span><span class="sxs-lookup"><span data-stu-id="17eb9-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="17eb9-117">プロパティの値は変数または定数の場合と同様に式に含められるか、または代入ステートメントの左辺にある変数またはプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="17eb9-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17eb9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="17eb9-118">See also</span></span>

- [<span data-ttu-id="17eb9-119">手順</span><span class="sxs-lookup"><span data-stu-id="17eb9-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="17eb9-120">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="17eb9-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="17eb9-121">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="17eb9-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="17eb9-122">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="17eb9-122">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="17eb9-123">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="17eb9-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="17eb9-124">方法: プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="17eb9-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="17eb9-125">方法: 複数のアクセス レベルを持つプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="17eb9-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="17eb9-126">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="17eb9-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="17eb9-127">方法: 既定のプロパティを宣言して呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17eb9-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="17eb9-128">方法: プロパティに値を格納する</span><span class="sxs-lookup"><span data-stu-id="17eb9-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
