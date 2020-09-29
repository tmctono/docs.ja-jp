---
title: '方法: 列挙値に関連付けられている文字列を確認する'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 4138759bfbb049b77406fc536219b40d3ed9e2a5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058770"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="9bf3c-102">方法: 列挙値に関連付けられている文字列を確認する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bf3c-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>

<span data-ttu-id="9bf3c-103"><xref:System.Enum.GetValues%2A> メソッドと <xref:System.Enum.GetNames%2A> メソッドを使用することで、列挙型メンバーに関連付けられている文字列と値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9bf3c-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="9bf3c-104">列挙型に関連付けられている文字列を確認するには</span><span class="sxs-lookup"><span data-stu-id="9bf3c-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="9bf3c-105">列挙型メンバーに関連付けられている文字列を取得するには、<xref:System.Enum.GetNames%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bf3c-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="9bf3c-106">次の例では、列挙型 `flavorEnum` を宣言してから、各メンバーに関連付けられている文字列を <xref:System.Enum.GetNames%2A> メソッドにより表示します。</span><span class="sxs-lookup"><span data-stu-id="9bf3c-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9bf3c-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bf3c-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="9bf3c-108">方法: 列挙型を宣言する</span><span class="sxs-lookup"><span data-stu-id="9bf3c-108">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="9bf3c-109">方法: 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="9bf3c-109">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="9bf3c-110">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="9bf3c-110">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="9bf3c-111">方法: Visual Basic で列挙型を反復処理する</span><span class="sxs-lookup"><span data-stu-id="9bf3c-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="9bf3c-112">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="9bf3c-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="9bf3c-113">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="9bf3c-113">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
