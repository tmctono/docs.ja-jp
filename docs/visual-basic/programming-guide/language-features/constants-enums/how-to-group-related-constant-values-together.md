---
title: '方法: グループ関連する定数値 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: a4f74e48cfdd5c0bc0f745d0f32eb39442f5bd83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333329"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="529ce-102">方法: グループ関連する定数値 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="529ce-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="529ce-103">列挙型は、関連する定数をグループ化する最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="529ce-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="529ce-104">持つ列挙体を作成する、`Enum`クラスまたはモジュールの宣言セクション内のステートメント。</span><span class="sxs-lookup"><span data-stu-id="529ce-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="529ce-105">詳細については、「[方法 :列挙型を宣言](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)します。</span><span class="sxs-lookup"><span data-stu-id="529ce-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="529ce-106">グループに関連する定数値</span><span class="sxs-lookup"><span data-stu-id="529ce-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="529ce-107">コードのアクセス レベルを含む宣言を記述、`Enum`キーワード、および有効な名前。</span><span class="sxs-lookup"><span data-stu-id="529ce-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="529ce-108">この例で作成、`Private`列挙型、`temperatureValues`します。</span><span class="sxs-lookup"><span data-stu-id="529ce-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="529ce-109">列挙体の定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="529ce-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="529ce-110">この例で作成、`Public`列挙`temperatureValues`し、その値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="529ce-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="529ce-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="529ce-111">See also</span></span>

- [<span data-ttu-id="529ce-112">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="529ce-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="529ce-113">方法: 列挙体のメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="529ce-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="529ce-114">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="529ce-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="529ce-115">定数の概要</span><span class="sxs-lookup"><span data-stu-id="529ce-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="529ce-116">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="529ce-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="529ce-117">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="529ce-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
