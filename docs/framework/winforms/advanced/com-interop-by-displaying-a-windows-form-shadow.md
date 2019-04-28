---
title: '方法: ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: 81220ad4c0bf00a38abfe7257d5fc61e92e8d885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779094"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="27dc8-102">方法: ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする</span><span class="sxs-lookup"><span data-stu-id="27dc8-102">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>
<span data-ttu-id="27dc8-103">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] メッセージ ループで Windows フォームを表示して、コンポーネント オブジェクト モデル (COM) 相互運用性の問題を解決できます。これは、 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> メソッドを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="27dc8-103">You can resolve Component Object Model (COM) interoperability problems by displaying your Windows Form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop, which is created by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="27dc8-104">フォームが COM クライアント アプリケーションから正しく動作するには、Windows フォームのメッセージ ループ上で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27dc8-104">To make a form work correctly from a COM client application, you must run it on a Windows Forms message loop.</span></span> <span data-ttu-id="27dc8-105">そのためには、次の方法のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="27dc8-105">To do this, use one of the following approaches:</span></span>  
  
- <span data-ttu-id="27dc8-106"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを使用して、Windows フォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="27dc8-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form;</span></span>  
  
- <span data-ttu-id="27dc8-107">各 Windows フォームを別のスレッドで表示します。</span><span class="sxs-lookup"><span data-stu-id="27dc8-107">Display each Windows Form on a separate thread.</span></span> <span data-ttu-id="27dc8-108">詳細については、「[方法 :独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポート](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)します。</span><span class="sxs-lookup"><span data-stu-id="27dc8-108">For more information, see [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="27dc8-109">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="27dc8-109">Procedure</span></span>  
 <span data-ttu-id="27dc8-110"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メッセージ ループにフォームを表示する方法としては、すべての方法の中で実装する必要があるコードが最も少ない [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] メソッドを使用する方法が最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="27dc8-110">Using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method can be the easiest way to display a form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop because, of all the approaches, it requires the least code to implement.</span></span>  
  
 <span data-ttu-id="27dc8-111"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドは、管理されていないアプリケーションのメッセージ ループを一時停止し、フォームをダイアログ ボックスとして表示します。</span><span class="sxs-lookup"><span data-stu-id="27dc8-111">The <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method suspends the unmanaged application's message loop and displays the form as a dialog box.</span></span> <span data-ttu-id="27dc8-112">ホスト アプリケーションのメッセージ ループが一時停止されているので、 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドは、新しい [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] メッセージ ループを作成してフォームのメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="27dc8-112">Because the host application's message loop has been suspended, the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method creates a new [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop to process the form's messages.</span></span>  
  
 <span data-ttu-id="27dc8-113"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを使用する場合の欠点は、フォームがモーダル ダイアログ ボックスとして開かれることです。</span><span class="sxs-lookup"><span data-stu-id="27dc8-113">The disadvantage of using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method is that the form will be opened as a modal dialog box.</span></span> <span data-ttu-id="27dc8-114">この動作により、Windows フォームが開かれている間は呼び出し元のアプリケーションですべてのユーザー インターフェイス (UI) がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="27dc8-114">This behavior blocks any user interface (UI) in the calling application while the Windows Form is open.</span></span> <span data-ttu-id="27dc8-115">ユーザーがフォームを終了すると、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] メッセージ ループが終了し、以前のアプリケーションのメッセージ ループの実行が再び開始されます。</span><span class="sxs-lookup"><span data-stu-id="27dc8-115">When the user exits the form, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop closes and the earlier application's message loop starts running again.</span></span>  
  
 <span data-ttu-id="27dc8-116">フォームを表示するためのメソッドが含まれるクラス ライブラリを Windows フォームで作成し、その後で COM 相互運用機能のクラス ライブラリをビルドすることができます。</span><span class="sxs-lookup"><span data-stu-id="27dc8-116">You can create a class library in Windows Forms which has a method to show the form, and then build the class library for COM interop.</span></span> <span data-ttu-id="27dc8-117">Visual Basic 6.0 または Microsoft Foundation Classes (MFC) からこの DLL ファイルを使用し、これらのいずれかの環境から <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを呼び出してフォームを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="27dc8-117">You can use this DLL file from Visual Basic 6.0 or Microsoft Foundation Classes (MFC), and from either of these environments you can call the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the form.</span></span>  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="27dc8-118">ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする方法</span><span class="sxs-lookup"><span data-stu-id="27dc8-118">To support COM interop by displaying a windows form with the ShowDialog method</span></span>  
  
- <span data-ttu-id="27dc8-119"><xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> コンポーネントで、 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドのすべての呼び出しを [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] メソッドの呼び出しに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="27dc8-119">Replace all calls to the <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> method with calls to the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method in your [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27dc8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="27dc8-120">See also</span></span>

- [<span data-ttu-id="27dc8-121">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="27dc8-121">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="27dc8-122">方法: 独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="27dc8-122">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [<span data-ttu-id="27dc8-123">Windows Forms and Unmanaged Applications</span><span class="sxs-lookup"><span data-stu-id="27dc8-123">Windows Forms and Unmanaged Applications</span></span>](windows-forms-and-unmanaged-applications.md)
