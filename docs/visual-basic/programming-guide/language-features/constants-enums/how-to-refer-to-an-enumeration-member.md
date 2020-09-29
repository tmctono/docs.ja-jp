---
title: '方法: 列挙型のメンバーを参照する'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: d1b239e7d6be3ebf1e64d6589a4cc14dce8946f5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095669"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="bacad-102">方法: 列挙型のメンバーを参照する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bacad-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>

<span data-ttu-id="bacad-103">一連の関連する定数を操作する場合や、定数値に名前を関連付ける場合は、列挙型を使うと便利です。</span><span class="sxs-lookup"><span data-stu-id="bacad-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="bacad-104">たとえば、一連の整数型の定数を曜日に関連付けて列挙型として宣言すると、コードで整数値ではなく曜日名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="bacad-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="bacad-105">`Imports` ステートメントを使用することで、完全修飾名の使用を回避できます。</span><span class="sxs-lookup"><span data-stu-id="bacad-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="bacad-106">詳細については、[列挙型と名前の修飾](enumerations-and-name-qualification.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bacad-106">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="bacad-107">列挙型のメンバーを参照するには</span><span class="sxs-lookup"><span data-stu-id="bacad-107">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="bacad-108">列挙型でメンバー名を修飾します。</span><span class="sxs-lookup"><span data-stu-id="bacad-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="bacad-109">たとえば、次の例では、`FirstDayOfWeek` 列挙型の `Saturday` メンバーを変数 `DayValue` に割り当てています。</span><span class="sxs-lookup"><span data-stu-id="bacad-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="bacad-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bacad-110">See also</span></span>

- [<span data-ttu-id="bacad-111">方法: 列挙型を宣言する</span><span class="sxs-lookup"><span data-stu-id="bacad-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="bacad-112">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="bacad-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="bacad-113">方法: Visual Basic で列挙型を反復処理する</span><span class="sxs-lookup"><span data-stu-id="bacad-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="bacad-114">方法: 列挙値に関連付けられている文字列を確認する</span><span class="sxs-lookup"><span data-stu-id="bacad-114">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="bacad-115">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="bacad-115">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
