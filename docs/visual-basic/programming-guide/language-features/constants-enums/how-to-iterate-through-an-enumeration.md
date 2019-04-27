---
title: '方法: Visual Basic で列挙型を反復処理します。'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 63597145e96b04affc5f0e80e05a56b3fdf27278
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907037"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="1daf6-102">方法: Visual Basic で列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="1daf6-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="1daf6-103">一連の関連する定数を操作する場合や、定数値に名前を関連付ける場合は、列挙型を使うと便利です。</span><span class="sxs-lookup"><span data-stu-id="1daf6-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="1daf6-104">列挙体を反復処理に移動できますを使用して、配列に、<xref:System.Enum.GetValues%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="1daf6-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="1daf6-105">使用して、列挙を反復処理することも、`For...Each`ステートメントを使用して、<xref:System.Enum.GetNames%2A>または<xref:System.Enum.GetValues%2A>文字列または数値の値を抽出するメソッド。</span><span class="sxs-lookup"><span data-stu-id="1daf6-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="1daf6-106">列挙体を反復処理するには</span><span class="sxs-lookup"><span data-stu-id="1daf6-106">To iterate through an enumeration</span></span>  
  
-   <span data-ttu-id="1daf6-107">配列を宣言しを使って、列挙型を変換、<xref:System.Enum.GetValues%2A>こととして、配列を渡す前にメソッドは、他の変数。</span><span class="sxs-lookup"><span data-stu-id="1daf6-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="1daf6-108">次の例は、列挙体の各メンバーを表示します。<xref:Microsoft.VisualBasic.FirstDayOfWeek>ように、列挙体で反復処理します。</span><span class="sxs-lookup"><span data-stu-id="1daf6-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="1daf6-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="1daf6-109">See also</span></span>

- [<span data-ttu-id="1daf6-110">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="1daf6-110">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="1daf6-111">方法: 列挙体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="1daf6-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="1daf6-112">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="1daf6-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="1daf6-113">方法: 列挙値に関連付けられている文字列を確認します。</span><span class="sxs-lookup"><span data-stu-id="1daf6-113">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="1daf6-114">方法: 列挙体のメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1daf6-114">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="1daf6-115">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="1daf6-115">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="1daf6-116">配列</span><span class="sxs-lookup"><span data-stu-id="1daf6-116">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
