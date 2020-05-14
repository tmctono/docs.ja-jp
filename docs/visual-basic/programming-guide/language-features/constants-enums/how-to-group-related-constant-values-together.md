---
title: '方法: 関連する定数値をまとめてグループ化する'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 151eefee4f69e1db8ba40f91334da8a051b95732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354041"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="8fcc2-102">方法: 関連する定数値をまとめてグループ化する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fcc2-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="8fcc2-103">関連する定数をまとめてグループ化するには、列挙型が最適です。</span><span class="sxs-lookup"><span data-stu-id="8fcc2-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="8fcc2-104">列挙型は、クラスまたはモジュールの宣言セクションで `Enum` ステートメントを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="8fcc2-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="8fcc2-105">詳細については、[列挙型の宣言方法](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fcc2-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="8fcc2-106">関連する定数値をグループ化するには</span><span class="sxs-lookup"><span data-stu-id="8fcc2-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="8fcc2-107">コード アクセス レベル、`Enum` キーワード、有効な名前を含む宣言を記述します。</span><span class="sxs-lookup"><span data-stu-id="8fcc2-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="8fcc2-108">次の例では、`Private` の列挙型 `temperatureValues` を作成しています。</span><span class="sxs-lookup"><span data-stu-id="8fcc2-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="8fcc2-109">列挙型の定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="8fcc2-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="8fcc2-110">次の例では、`Public` の `temperatureValues` 列挙型を作成して、値を割り当てています。</span><span class="sxs-lookup"><span data-stu-id="8fcc2-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8fcc2-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fcc2-111">See also</span></span>

- [<span data-ttu-id="8fcc2-112">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="8fcc2-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="8fcc2-113">方法: 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="8fcc2-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="8fcc2-114">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="8fcc2-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="8fcc2-115">定数の概要</span><span class="sxs-lookup"><span data-stu-id="8fcc2-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="8fcc2-116">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="8fcc2-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="8fcc2-117">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="8fcc2-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
