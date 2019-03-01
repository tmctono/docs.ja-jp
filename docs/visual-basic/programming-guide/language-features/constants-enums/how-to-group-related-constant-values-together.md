---
title: '方法: グループ関連する定数値 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 63475487c8a35f5b306b28d4e7097324bef00d85
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977826"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="6bcc5-102">方法: グループ関連する定数値 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6bcc5-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="6bcc5-103">列挙型は、関連する定数をグループ化する最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="6bcc5-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="6bcc5-104">持つ列挙体を作成する、`Enum`クラスまたはモジュールの宣言セクション内のステートメント。</span><span class="sxs-lookup"><span data-stu-id="6bcc5-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="6bcc5-105">詳細については、「[方法 :列挙型を宣言](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bcc5-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="6bcc5-106">グループに関連する定数値</span><span class="sxs-lookup"><span data-stu-id="6bcc5-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="6bcc5-107">コードのアクセス レベルを含む宣言を記述、`Enum`キーワード、および有効な名前。</span><span class="sxs-lookup"><span data-stu-id="6bcc5-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="6bcc5-108">この例で作成、`Private`列挙型、`temperatureValues`します。</span><span class="sxs-lookup"><span data-stu-id="6bcc5-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2.  <span data-ttu-id="6bcc5-109">列挙体の定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="6bcc5-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="6bcc5-110">この例で作成、`Public`列挙`temperatureValues`し、その値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6bcc5-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6bcc5-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bcc5-111">See also</span></span>
- [<span data-ttu-id="6bcc5-112">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="6bcc5-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="6bcc5-113">方法: 列挙体のメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcc5-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="6bcc5-114">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="6bcc5-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="6bcc5-115">定数の概要</span><span class="sxs-lookup"><span data-stu-id="6bcc5-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="6bcc5-116">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="6bcc5-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="6bcc5-117">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="6bcc5-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
