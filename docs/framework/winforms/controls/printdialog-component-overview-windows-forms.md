---
title: PrintDialog コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 982c52dbe9243e69bbb0452513e78798f4d1fd0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903410"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="9235a-102">PrintDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="9235a-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="9235a-103">Windows フォーム[PrintDialog](printdialog-component-windows-forms.md)コンポーネントは構成済みのダイアログ ボックスがプリンターを選択し、印刷するページを選択して、Windows ベースのアプリケーションで他の印刷関連の設定を決定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9235a-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="9235a-104">独自のダイアログ ボックスを構成する代わりに、プリンターと印刷関連の設定の選択のための簡単なソリューションとして使用します。</span><span class="sxs-lookup"><span data-stu-id="9235a-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="9235a-105">ユーザーが自分のドキュメントの多くの部分の印刷を有効にすることができます。 すべてを印刷、印刷を選択したページ範囲または選択範囲を印刷します。</span><span class="sxs-lookup"><span data-stu-id="9235a-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="9235a-106">Windows の標準のダイアログ ボックスを使用して、ユーザーがすぐに慣れる基本的な機能を持つアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9235a-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="9235a-107"><xref:System.Windows.Forms.PrintDialog>コンポーネントが継承、<xref:System.Windows.Forms.CommonDialog>クラス。</span><span class="sxs-lookup"><span data-stu-id="9235a-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="9235a-108">コンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="9235a-108">Working with the Component</span></span>  
 <span data-ttu-id="9235a-109">使用して、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッドを実行時にダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="9235a-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="9235a-110">このコンポーネントには 1 つの印刷ジョブをいずれかに関連するプロパティ (<xref:System.Drawing.Printing.PrintDocument>クラス)、または個々 のプリンターの設定 (<xref:System.Drawing.Printing.PrinterSettings>クラス)。</span><span class="sxs-lookup"><span data-stu-id="9235a-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="9235a-111">さらに、これらのうち、いずれかには複数のプリンターで共有することがあります。</span><span class="sxs-lookup"><span data-stu-id="9235a-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="9235a-112">フォームに追加されたとき、<xref:System.Windows.Forms.PrintDialog>コンポーネント、Windows フォーム デザイナーの下部にあるトレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9235a-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9235a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9235a-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="9235a-114">PrintDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9235a-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
