---
title: Windows フォーム コントロールのマルチスレッド処理
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012725"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="b3b77-102">Windows フォーム コントロールのマルチスレッド処理</span><span class="sxs-lookup"><span data-stu-id="b3b77-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="b3b77-103">多くのアプリケーションで行うことができます、ユーザー インターフェイス (UI) の高い別のスレッドで時間のかかる操作を実行することによって。</span><span class="sxs-lookup"><span data-stu-id="b3b77-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="b3b77-104">多数のツールがあるマルチ スレッドなど、Windows フォーム コントロール、<xref:System.Threading>名前空間、<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>メソッド、および`BackgroundWorker`コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="b3b77-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3b77-105">`BackgroundWorker`コンポーネントが置換および機能を追加、<xref:System.Threading>名前空間と<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>メソッドです。 ただし、これらは保持されます下位互換性と将来の使用を選択した場合。</span><span class="sxs-lookup"><span data-stu-id="b3b77-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="b3b77-106">詳細については、次を参照してください。 [BackgroundWorker コンポーネントの概要](backgroundworker-component-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3b77-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3b77-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b3b77-107">In This Section</span></span>  
 [<span data-ttu-id="b3b77-108">方法: Windows フォーム コントロールのスレッド セーフな呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="b3b77-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="b3b77-109">Windows フォーム コントロールをスレッド セーフな呼び出しを作成する方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="b3b77-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="b3b77-110">方法: ファイルを検索するバック グラウンド スレッドを使用して、</span><span class="sxs-lookup"><span data-stu-id="b3b77-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="b3b77-111">使用する方法を示しています、<xref:System.Threading>名前空間と<xref:System.Windows.Forms.Control.BeginInvoke%2A>メソッドを非同期的にファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="b3b77-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b3b77-112">参照</span><span class="sxs-lookup"><span data-stu-id="b3b77-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="b3b77-113">非同期操作のワーカー スレッドをカプセル化するコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3b77-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="b3b77-114">サウンドを非同期的に読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3b77-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="b3b77-115">イメージを非同期的に読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3b77-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b3b77-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3b77-116">Related Sections</span></span>  
 [<span data-ttu-id="b3b77-117">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="b3b77-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="b3b77-118">時間のかかる操作を行う方法を示しています、<xref:System.ComponentModel.BackgroundWorker>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="b3b77-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="b3b77-119">BackgroundWorker コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="b3b77-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="b3b77-120">使用する方法について説明するトピックを示します、<xref:System.ComponentModel.BackgroundWorker>コンポーネントの非同期操作をします。</span><span class="sxs-lookup"><span data-stu-id="b3b77-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
