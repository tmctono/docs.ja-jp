---
title: '方法 : 関連する定数値をまとめてグループ化する'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 151eefee4f69e1db8ba40f91334da8a051b95732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354041"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="f39d0-102">方法: 関連する定数値をまとめてグループ化する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f39d0-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="f39d0-103">列挙は、関連する定数をグループ化するための最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="f39d0-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="f39d0-104">列挙体を作成するには、クラスまたはモジュールの宣言セクションにある `Enum` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f39d0-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="f39d0-105">詳細については、「[方法: 列挙型を宣言](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f39d0-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="f39d0-106">関連する定数値をグループ化するには</span><span class="sxs-lookup"><span data-stu-id="f39d0-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="f39d0-107">コードアクセスレベル、`Enum` キーワード、および有効な名前を含む宣言を記述します。</span><span class="sxs-lookup"><span data-stu-id="f39d0-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="f39d0-108">この例では、`Private` 列挙型、`temperatureValues`を作成します。</span><span class="sxs-lookup"><span data-stu-id="f39d0-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="f39d0-109">列挙体の定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="f39d0-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="f39d0-110">この例では、`Public` 列挙 `temperatureValues` を作成し、その値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f39d0-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f39d0-111">参照</span><span class="sxs-lookup"><span data-stu-id="f39d0-111">See also</span></span>

- [<span data-ttu-id="f39d0-112">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="f39d0-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="f39d0-113">方法 : 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="f39d0-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="f39d0-114">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="f39d0-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="f39d0-115">定数の概要</span><span class="sxs-lookup"><span data-stu-id="f39d0-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="f39d0-116">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="f39d0-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="f39d0-117">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="f39d0-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
