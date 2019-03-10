---
title: PageSetupDialog コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 702e9a40652e00cc2f93dd52af29a61a50c90ae0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715803"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="4593b-102">PageSetupDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="4593b-102">PageSetupDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="4593b-103">Windows フォーム<xref:System.Windows.Forms.PageSetupDialog>コンポーネントは Windows ベースのアプリケーションの印刷用ページの詳細を設定するための事前構成済みダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4593b-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="4593b-104">代わりに、独自のダイアログ ボックスの構成ページの基本設定を設定するのにユーザーの簡単な解決策として、Windows ベース アプリケーションの中で使用します。</span><span class="sxs-lookup"><span data-stu-id="4593b-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="4593b-105">ユーザーに境界線と余白の調整、ヘッダーとフッター、および縦または横方向の設定を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4593b-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="4593b-106">Windows の標準のダイアログ ボックスを使用して、ユーザーがすぐに慣れる基本的な機能を持つアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4593b-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="4593b-107">キー プロパティとメソッド</span><span class="sxs-lookup"><span data-stu-id="4593b-107">Key Properties and Methods</span></span>  
 <span data-ttu-id="4593b-108">使用して、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッド実行時にダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="4593b-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="4593b-109">このコンポーネントには 1 つのページのいずれかに関連するプロパティを設定できます (<xref:System.Drawing.Printing.PrintDocument>クラス)、または任意のドキュメント (<xref:System.Drawing.Printing.PageSettings>クラス)。</span><span class="sxs-lookup"><span data-stu-id="4593b-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="4593b-110">さらに、<xref:System.Windows.Forms.PageSetupDialog>に格納されている特定のプリンター設定を確認するコンポーネントを使用できます、<xref:System.Drawing.Printing.PrinterSettings>クラス。</span><span class="sxs-lookup"><span data-stu-id="4593b-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>  
  
 <span data-ttu-id="4593b-111">フォームに追加されたとき、<xref:System.Windows.Forms.PageSetupDialog>コンポーネント、Windows フォーム デザイナーの下部にあるトレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4593b-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4593b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4593b-112">See also</span></span>
- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="4593b-113">PageSetupDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4593b-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
