---
title: '方法: 列挙型を反復処理する'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: fb6fbdd45ca0e84ccb9fc55296d78e3867d5fe25
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414428"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="5d817-102">方法: Visual Basic で列挙型を反復処理する</span><span class="sxs-lookup"><span data-stu-id="5d817-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="5d817-103">一連の関連する定数を操作する場合や、定数値に名前を関連付ける場合は、列挙型を使うと便利です。</span><span class="sxs-lookup"><span data-stu-id="5d817-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="5d817-104"><xref:System.Enum.GetValues%2A> メソッドを使用して列挙型を配列に入れると、列挙型の反復処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5d817-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="5d817-105">また、`For...Each` ステートメント、<xref:System.Enum.GetNames%2A> メソッド、または <xref:System.Enum.GetValues%2A> メソッドを使用して列挙型の反復処理を行うと、文字列値または数値を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="5d817-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="5d817-106">列挙型を反復処理するには</span><span class="sxs-lookup"><span data-stu-id="5d817-106">To iterate through an enumeration</span></span>  
  
- <span data-ttu-id="5d817-107">他の変数の場合と同様に、配列を宣言して <xref:System.Enum.GetValues%2A> メソッドにより列挙型をその配列に変換してから、配列を渡します。</span><span class="sxs-lookup"><span data-stu-id="5d817-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="5d817-108">次の例では、列挙型 <xref:Microsoft.VisualBasic.FirstDayOfWeek> の反復処理の進捗に応じて、この列挙型の各メンバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d817-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="5d817-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d817-109">See also</span></span>

- [<span data-ttu-id="5d817-110">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="5d817-110">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="5d817-111">方法: 列挙型を宣言する</span><span class="sxs-lookup"><span data-stu-id="5d817-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="5d817-112">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="5d817-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="5d817-113">方法: 列挙値に関連付けられている文字列を確認する</span><span class="sxs-lookup"><span data-stu-id="5d817-113">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="5d817-114">方法: 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="5d817-114">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="5d817-115">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="5d817-115">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="5d817-116">配列</span><span class="sxs-lookup"><span data-stu-id="5d817-116">Arrays</span></span>](../arrays/index.md)
