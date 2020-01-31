---
title: コントロールでのマルチスレッド
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742143"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="aef7d-102">Windows フォーム コントロールのマルチスレッド処理</span><span class="sxs-lookup"><span data-stu-id="aef7d-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="aef7d-103">多くのアプリケーションでは、別のスレッドで時間のかかる操作を実行することで、ユーザーインターフェイス (UI) の応答性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="aef7d-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="aef7d-104"><xref:System.Threading> 名前空間、<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> メソッド、`BackgroundWorker` コンポーネントなど、Windows フォームコントロールのマルチスレッドには多数のツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="aef7d-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aef7d-105">`BackgroundWorker` コンポーネントによって、<xref:System.Threading> 名前空間と <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> メソッドに置き換えられ、機能が追加されます。ただし、これらは下位互換性と将来の使用の両方のために保持されます (選択した場合)。</span><span class="sxs-lookup"><span data-stu-id="aef7d-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="aef7d-106">詳細については、「 [BackgroundWorker コンポーネントの概要](backgroundworker-component-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aef7d-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aef7d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aef7d-107">In This Section</span></span>  
 [<span data-ttu-id="aef7d-108">方法: Windows フォーム コントロールのスレッド セーフな呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="aef7d-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="aef7d-109">Windows フォームコントロールに対してスレッドセーフな呼び出しを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="aef7d-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="aef7d-110">方法: バックグラウンド スレッドを使用してファイルを検索する</span><span class="sxs-lookup"><span data-stu-id="aef7d-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="aef7d-111"><xref:System.Threading> 名前空間と <xref:System.Windows.Forms.Control.BeginInvoke%2A> メソッドを使用してファイルを非同期的に検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aef7d-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="aef7d-112">参照先</span><span class="sxs-lookup"><span data-stu-id="aef7d-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="aef7d-113">非同期操作のワーカースレッドをカプセル化するコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aef7d-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="aef7d-114">サウンドを非同期に読み込む方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="aef7d-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="aef7d-115">画像を非同期に読み込む方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="aef7d-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aef7d-116">関連セクション</span><span class="sxs-lookup"><span data-stu-id="aef7d-116">Related Sections</span></span>  
 [<span data-ttu-id="aef7d-117">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="aef7d-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="aef7d-118"><xref:System.ComponentModel.BackgroundWorker> コンポーネントで時間のかかる操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aef7d-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="aef7d-119">BackgroundWorker コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="aef7d-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="aef7d-120">非同期操作に <xref:System.ComponentModel.BackgroundWorker> コンポーネントを使用する方法について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="aef7d-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
