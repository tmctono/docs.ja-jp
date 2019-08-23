---
title: Windows フォーム コントロールのマルチスレッド処理
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cf6790172b7445ad154eead5d17f8efddd78ffee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952679"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="05f17-102">Windows フォーム コントロールのマルチスレッド処理</span><span class="sxs-lookup"><span data-stu-id="05f17-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="05f17-103">多くのアプリケーションでは、別のスレッドで時間のかかる操作を実行することで、ユーザーインターフェイス (UI) の応答性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="05f17-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="05f17-104"><xref:System.Threading>名前空間`BackgroundWorker` 、メソッド、コンポーネントなど、Windows フォームコントロールのマルチスレッドでは、さまざまなツールを使用できます。 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="05f17-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05f17-105">コンポーネント`BackgroundWorker`は、 <xref:System.Threading>名前空間と<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>メソッドに置き換えられ、機能を追加します。ただし、これらは下位互換性と将来の使用の両方のために保持されます (選択した場合)。</span><span class="sxs-lookup"><span data-stu-id="05f17-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="05f17-106">詳細については、「 [BackgroundWorker コンポーネントの概要](backgroundworker-component-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05f17-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05f17-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="05f17-107">In This Section</span></span>  
 [<span data-ttu-id="05f17-108">方法: Windows フォームコントロールに対してスレッドセーフな呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="05f17-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="05f17-109">Windows フォームコントロールに対してスレッドセーフな呼び出しを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="05f17-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="05f17-110">方法: バックグラウンドスレッドを使用してファイルを検索する</span><span class="sxs-lookup"><span data-stu-id="05f17-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="05f17-111"><xref:System.Threading>名前空間<xref:System.Windows.Forms.Control.BeginInvoke%2A>とメソッドを使用して、ファイルを非同期的に検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="05f17-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="05f17-112">参照</span><span class="sxs-lookup"><span data-stu-id="05f17-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="05f17-113">非同期操作のワーカースレッドをカプセル化するコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="05f17-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="05f17-114">サウンドを非同期に読み込む方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="05f17-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="05f17-115">画像を非同期に読み込む方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="05f17-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="05f17-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="05f17-116">Related Sections</span></span>  
 [<span data-ttu-id="05f17-117">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="05f17-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="05f17-118"><xref:System.ComponentModel.BackgroundWorker>コンポーネントで時間のかかる操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="05f17-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="05f17-119">BackgroundWorker コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="05f17-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="05f17-120"><xref:System.ComponentModel.BackgroundWorker>コンポーネントを非同期操作に使用する方法について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="05f17-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
