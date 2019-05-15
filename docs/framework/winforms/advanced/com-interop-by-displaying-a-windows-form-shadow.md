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
ms.openlocfilehash: f2fb48e07243694b14904b240bdcb0739175c2fc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593534"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="90875-102">方法: ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする</span><span class="sxs-lookup"><span data-stu-id="90875-102">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>
<span data-ttu-id="90875-103">使用して作成された .NET Framework のメッセージ ループ上の Windows フォームを表示して、コンポーネント オブジェクト モデル (COM) 相互運用性の問題を解決することができます、<xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="90875-103">You can resolve Component Object Model (COM) interoperability problems by displaying your Windows Form on a .NET Framework message loop, which is created by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="90875-104">フォームが COM クライアント アプリケーションから正しく動作するには、Windows フォームのメッセージ ループ上で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90875-104">To make a form work correctly from a COM client application, you must run it on a Windows Forms message loop.</span></span> <span data-ttu-id="90875-105">そのためには、次の方法のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="90875-105">To do this, use one of the following approaches:</span></span>  
  
- <span data-ttu-id="90875-106"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを使用して、Windows フォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="90875-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form;</span></span>  
  
- <span data-ttu-id="90875-107">各 Windows フォームを別のスレッドで表示します。</span><span class="sxs-lookup"><span data-stu-id="90875-107">Display each Windows Form on a separate thread.</span></span> <span data-ttu-id="90875-108">詳細については、「[方法 :独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポート](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)します。</span><span class="sxs-lookup"><span data-stu-id="90875-108">For more information, see [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="90875-109">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="90875-109">Procedure</span></span>  
 <span data-ttu-id="90875-110">使用して、<xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>メソッドはできるため、.NET Framework のメッセージ ループでフォームを表示する最も簡単な方法は、すべての方法の最小限のコードを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90875-110">Using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method can be the easiest way to display a form on a .NET Framework message loop because, of all the approaches, it requires the least code to implement.</span></span>  
  
 <span data-ttu-id="90875-111"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドは、管理されていないアプリケーションのメッセージ ループを一時停止し、フォームをダイアログ ボックスとして表示します。</span><span class="sxs-lookup"><span data-stu-id="90875-111">The <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method suspends the unmanaged application's message loop and displays the form as a dialog box.</span></span> <span data-ttu-id="90875-112">ホスト アプリケーションのメッセージ ループが中断されているため、<xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>メソッドは、フォームのメッセージを処理する新しい .NET Framework メッセージ ループを作成します。</span><span class="sxs-lookup"><span data-stu-id="90875-112">Because the host application's message loop has been suspended, the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method creates a new .NET Framework message loop to process the form's messages.</span></span>  
  
 <span data-ttu-id="90875-113"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを使用する場合の欠点は、フォームがモーダル ダイアログ ボックスとして開かれることです。</span><span class="sxs-lookup"><span data-stu-id="90875-113">The disadvantage of using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method is that the form will be opened as a modal dialog box.</span></span> <span data-ttu-id="90875-114">この動作により、Windows フォームが開かれている間は呼び出し元のアプリケーションですべてのユーザー インターフェイス (UI) がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="90875-114">This behavior blocks any user interface (UI) in the calling application while the Windows Form is open.</span></span> <span data-ttu-id="90875-115">ユーザーは、フォームを終了すると、.NET Framework のメッセージ ループが閉じし、アプリケーションの以前のメッセージ ループの実行が再開します。</span><span class="sxs-lookup"><span data-stu-id="90875-115">When the user exits the form, the .NET Framework message loop closes and the earlier application's message loop starts running again.</span></span>  
  
 <span data-ttu-id="90875-116">フォームを表示するためのメソッドが含まれるクラス ライブラリを Windows フォームで作成し、その後で COM 相互運用機能のクラス ライブラリをビルドすることができます。</span><span class="sxs-lookup"><span data-stu-id="90875-116">You can create a class library in Windows Forms which has a method to show the form, and then build the class library for COM interop.</span></span> <span data-ttu-id="90875-117">Visual Basic 6.0 または Microsoft Foundation Classes (MFC) からこの DLL ファイルを使用し、これらのいずれかの環境から <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを呼び出してフォームを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="90875-117">You can use this DLL file from Visual Basic 6.0 or Microsoft Foundation Classes (MFC), and from either of these environments you can call the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the form.</span></span>  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="90875-118">ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする方法</span><span class="sxs-lookup"><span data-stu-id="90875-118">To support COM interop by displaying a windows form with the ShowDialog method</span></span>  
  
- <span data-ttu-id="90875-119">すべての呼び出しを置き換える、<xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType>メソッドの呼び出しを<xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>.NET Framework コンポーネントのメソッド。</span><span class="sxs-lookup"><span data-stu-id="90875-119">Replace all calls to the <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> method with calls to the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method in your .NET Framework component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90875-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="90875-120">See also</span></span>

- [<span data-ttu-id="90875-121">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="90875-121">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="90875-122">方法: 独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="90875-122">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [<span data-ttu-id="90875-123">Windows フォームとアンマネージ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="90875-123">Windows Forms and Unmanaged Applications</span></span>](windows-forms-and-unmanaged-applications.md)
