---
title: PrintDocument コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 16a7f3a34ccb280f7bf91c52e29b20edc22130b9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928995"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="db077-102">PrintDocument コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="db077-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="db077-103">Windows フォーム [PrintDocument](printdocument-component-windows-forms.md) コンポーネントを使用して、印刷対象を示すプロパティを設定し、Windows ベースのアプリケーション内でドキュメントを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="db077-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="db077-104">このコンポーネントは、ドキュメント印刷のあらゆる側面を制御するために、[PrintDialog](printdialog-component-windows-forms.md) コンポーネントと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="db077-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="db077-105">PrintDocument コンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="db077-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="db077-106">コンポーネントに<xref:System.Drawing.Printing.PrintDocument>関連する主なシナリオは、次の2つです。</span><span class="sxs-lookup"><span data-stu-id="db077-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="db077-107">簡易印刷ジョブ (個々のテキスト ファイルを印刷する場合など)。</span><span class="sxs-lookup"><span data-stu-id="db077-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="db077-108">このような場合は、 <xref:System.Drawing.Printing.PrintDocument>コンポーネントを Windows フォームに追加し、 <xref:System.Drawing.Printing.PrintDocument.PrintPage>イベントハンドラーでファイルを出力するプログラミングロジックを追加します。</span><span class="sxs-lookup"><span data-stu-id="db077-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="db077-109">プログラミングロジックは、ドキュメントを印刷<xref:System.Drawing.Printing.PrintDocument.Print%2A>するメソッドとなする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db077-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="db077-110">このメソッドは、 <xref:System.Drawing.Graphics> <xref:System.Drawing.Printing.PrintPageEventArgs>クラスの<xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>プロパティに含まれるオブジェクトをプリンターに送信します。</span><span class="sxs-lookup"><span data-stu-id="db077-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="db077-111"><xref:System.Drawing.Printing.PrintDocument>コンポーネントを使用してテキストドキュメントを印刷する方法を示す例につい[ては、「方法:Windows フォーム](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)で複数ページのテキストファイルを印刷します。</span><span class="sxs-lookup"><span data-stu-id="db077-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="db077-112">より複雑な印刷ジョブ (作成した印刷ロジックを再利用する場合など)。</span><span class="sxs-lookup"><span data-stu-id="db077-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="db077-113">この<xref:System.Drawing.Printing.PrintDocument>ような場合は、コンポーネントから新しいコンポーネントを派生させ、 <xref:System.Drawing.Printing.PrintDocument.PrintPage>イベントのオーバーライド (Visual Basic または[オーバーライド](../../../csharp/language-reference/keywords/override.md)[のオーバーライドを参照](../../../visual-basic/language-reference/modifiers/overrides.md) C#) を行います。</span><span class="sxs-lookup"><span data-stu-id="db077-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](../../../csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="db077-114">フォームに追加されると、 <xref:System.Drawing.Printing.PrintDocument> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db077-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="db077-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="db077-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="db077-116">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="db077-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="db077-117">PrintDocument コンポーネント</span><span class="sxs-lookup"><span data-stu-id="db077-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
