---
title: 列挙型と名前の修飾
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: 4121266447b771ba954ad52a46e0d8b88de3f9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347494"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="0a027-102">列挙型と名前修飾 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a027-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="0a027-103">通常、列挙体のメンバーを参照する場合は、列挙名でメンバー名を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a027-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="0a027-104">たとえば、`Days` 列挙体の `Sunday` メンバーを参照するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a027-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="0a027-105">Imports ステートメントの使用</span><span class="sxs-lookup"><span data-stu-id="0a027-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="0a027-106">次の例のように、コードの名前空間宣言セクションに `Imports` ステートメントを追加することで、完全修飾名を使用しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0a027-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 <span data-ttu-id="0a027-107">`Imports` ステートメントは、参照されるプロジェクトおよびアセンブリから名前空間名をインポートし、ステートメントが記述されているモジュールと同じプロジェクト内から名前空間名をインポートします。</span><span class="sxs-lookup"><span data-stu-id="0a027-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="0a027-108">このステートメントを追加すると、次の例のように、修飾子を使用せずに列挙メンバーを参照できます。</span><span class="sxs-lookup"><span data-stu-id="0a027-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 <span data-ttu-id="0a027-109">一連の関連する定数を列挙にまとめることによって、異なるコンテキストで同じ定数名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0a027-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="0a027-110">たとえば、`Days` と `WorkDays` の列挙体の曜日定数に同じ名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0a027-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="0a027-111">`Imports` ステートメントを列挙体と共に使用する場合は、あいまいな参照を避けるために注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a027-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="0a027-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0a027-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 <span data-ttu-id="0a027-113">`Monday` が `Days` 列挙と `Workdays` 列挙の両方のメンバーであると仮定すると、このコードはコンパイラエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="0a027-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="0a027-114">個々の定数を参照するときにあいまいな参照を回避するには、定数名を列挙体で修飾します。</span><span class="sxs-lookup"><span data-stu-id="0a027-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="0a027-115">次のコードは、`Days` と `WorkDays` 列挙体の `Saturday` 定数を参照します。</span><span class="sxs-lookup"><span data-stu-id="0a027-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="0a027-116">参照</span><span class="sxs-lookup"><span data-stu-id="0a027-116">See also</span></span>

- [<span data-ttu-id="0a027-117">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="0a027-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="0a027-118">方法: 列挙型を宣言する</span><span class="sxs-lookup"><span data-stu-id="0a027-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="0a027-119">方法 : 列挙型のメンバーを参照する</span><span class="sxs-lookup"><span data-stu-id="0a027-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="0a027-120">方法: Visual Basic 内の列挙体を反復処理する</span><span class="sxs-lookup"><span data-stu-id="0a027-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="0a027-121">方法 : 列挙値に関連付けられている文字列を確認する</span><span class="sxs-lookup"><span data-stu-id="0a027-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="0a027-122">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="0a027-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="0a027-123">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="0a027-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="0a027-124">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="0a027-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="0a027-125">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="0a027-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="0a027-126">データの種類</span><span class="sxs-lookup"><span data-stu-id="0a027-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
