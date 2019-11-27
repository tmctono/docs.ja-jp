---
title: '方法: 列挙体を反復処理する'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 6e8fd6760565a73d9d3b3d1d02fc872992eea354
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354021"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="dbb2d-102">方法 : Visual Basic で列挙型を反復処理する</span><span class="sxs-lookup"><span data-stu-id="dbb2d-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="dbb2d-103">一連の関連する定数を操作する場合や、定数値に名前を関連付ける場合は、列挙型を使うと便利です。</span><span class="sxs-lookup"><span data-stu-id="dbb2d-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="dbb2d-104">列挙体を反復処理するには、<xref:System.Enum.GetValues%2A> メソッドを使用して、その列挙型を配列に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbb2d-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="dbb2d-105">また、<xref:System.Enum.GetNames%2A> または <xref:System.Enum.GetValues%2A> メソッドを使用して文字列または数値を抽出し、`For...Each` ステートメントを使用して列挙を反復処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbb2d-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="dbb2d-106">列挙体を反復処理するには</span><span class="sxs-lookup"><span data-stu-id="dbb2d-106">To iterate through an enumeration</span></span>  
  
- <span data-ttu-id="dbb2d-107">配列を宣言し、他の変数と同様に配列を渡す前に、<xref:System.Enum.GetValues%2A> メソッドを使用して列挙体をその配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="dbb2d-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="dbb2d-108">次の例では、列挙型を反復処理するときに、列挙 <xref:Microsoft.VisualBasic.FirstDayOfWeek> の各メンバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="dbb2d-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="dbb2d-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbb2d-109">See also</span></span>

- [<span data-ttu-id="dbb2d-110">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="dbb2d-110">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="dbb2d-111">方法: 列挙型を宣言する</span><span class="sxs-lookup"><span data-stu-id="dbb2d-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="dbb2d-112">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="dbb2d-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="dbb2d-113">方法 : 列挙値に関連付けられている文字列を確認する</span><span class="sxs-lookup"><span data-stu-id="dbb2d-113">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="dbb2d-114">方法 : 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="dbb2d-114">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="dbb2d-115">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="dbb2d-115">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="dbb2d-116">配列</span><span class="sxs-lookup"><span data-stu-id="dbb2d-116">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
