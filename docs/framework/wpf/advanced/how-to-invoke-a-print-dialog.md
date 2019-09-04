---
title: '方法: 印刷ダイアログ ボックスを呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 4bad8158925fea8af529f70f92aad74e2a6bbec0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254112"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="17aa2-102">方法: 印刷ダイアログ ボックスを呼び出す</span><span class="sxs-lookup"><span data-stu-id="17aa2-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="17aa2-103">アプリケーションから印刷できるようにするには、単にオブジェクトを<xref:System.Windows.Controls.PrintDialog>作成して開くことができます。</span><span class="sxs-lookup"><span data-stu-id="17aa2-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17aa2-104">例</span><span class="sxs-lookup"><span data-stu-id="17aa2-104">Example</span></span>  
 <span data-ttu-id="17aa2-105">コントロール<xref:System.Windows.Controls.PrintDialog>は、、構成、および XPS [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]ジョブを送信するための1つのエントリポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="17aa2-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and XPS job submission.</span></span> <span data-ttu-id="17aa2-106">コントロールは使いやすく、マークアップまたはコードを使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]してインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="17aa2-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="17aa2-107">次の例では、コントロールをインスタンス化してコードで開く方法と、コントロールから出力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="17aa2-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="17aa2-108">また、ダイアログで特定の範囲のページを設定するオプションをユーザーに与える方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="17aa2-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="17aa2-109">このコード例では、C: ドライブのルートに FixedDocumentSequence ファイルがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="17aa2-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="17aa2-110">ダイアログが開いたら、ユーザーは自分のコンピューターにインストールされているプリンターから選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="17aa2-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="17aa2-111">また、 [MICROSOFT Xps ドキュメントライター](https://go.microsoft.com/fwlink/?LinkId=147319)を選択して、印刷ではなく XML Paper SPECIFICATION (XPS) ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="17aa2-111">They will also have the option of selecting the [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) to create an XML Paper Specification (XPS) file instead of printing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17aa2-112">このトピックで[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]説明されているの<xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType>コントロールは、Windows フォームのコンポーネントと混同しないようにする必要があります。 <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="17aa2-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="17aa2-113">厳密に言うと、ダイアログを<xref:System.Windows.Controls.PrintDialog.PrintDocument%2A>開くことなくメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="17aa2-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="17aa2-114">この意味では、コントロールは見えない印刷コンポーネントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="17aa2-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="17aa2-115">ただし、パフォーマンス上の理由から、メソッド<xref:System.Printing.PrintQueue.AddJob%2A> 、またはの多く<xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>のメソッドと<xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>メソッド<xref:System.Windows.Xps.XpsDocumentWriter>のいずれかを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="17aa2-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="17aa2-116">詳細については、「[プログラムによる XPS ファイルの印刷](how-to-programmatically-print-xps-files.md)」と「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17aa2-116">For more about this, see [Programmatically Print XPS Files](how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17aa2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="17aa2-117">See also</span></span>

- <xref:System.Windows.Controls.PrintDialog>
- [<span data-ttu-id="17aa2-118">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="17aa2-118">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="17aa2-119">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="17aa2-119">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="17aa2-120">Microsoft XPS ドキュメントライター</span><span class="sxs-lookup"><span data-stu-id="17aa2-120">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
