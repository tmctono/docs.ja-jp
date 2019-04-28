---
title: '方法: 列挙値 (Visual Basic) に関連付けられている文字列を確認します。'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 4fa04fa621347ae961975bfb636734e6c9df39fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906803"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="4cb44-102">方法: 列挙値 (Visual Basic) に関連付けられている文字列を確認します。</span><span class="sxs-lookup"><span data-stu-id="4cb44-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="4cb44-103"><xref:System.Enum.GetValues%2A>と<xref:System.Enum.GetNames%2A>メソッドを使用する文字列と列挙型メンバーに関連付けられている値を決定できます。</span><span class="sxs-lookup"><span data-stu-id="4cb44-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="4cb44-104">列挙体に関連付けられている文字列を決定するには</span><span class="sxs-lookup"><span data-stu-id="4cb44-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="4cb44-105">使用して、<xref:System.Enum.GetNames%2A>列挙型メンバーに関連付けられている文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="4cb44-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="4cb44-106">この例は、列挙体を宣言`flavorEnum`を使用して、<xref:System.Enum.GetNames%2A>各メンバーに関連付けられている文字列を表示するメソッド。</span><span class="sxs-lookup"><span data-stu-id="4cb44-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4cb44-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cb44-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="4cb44-108">方法: 列挙体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="4cb44-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="4cb44-109">方法: 列挙体のメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cb44-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="4cb44-110">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="4cb44-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="4cb44-111">方法: Visual Basic で列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="4cb44-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="4cb44-112">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="4cb44-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="4cb44-113">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="4cb44-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
