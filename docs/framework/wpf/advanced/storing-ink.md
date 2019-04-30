---
title: インクの格納
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
ms.openlocfilehash: 4089aa7942105c14eb628c75edb7f53ffacfaeb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053374"
---
# <a name="storing-ink"></a><span data-ttu-id="c8cf6-102">インクの格納</span><span class="sxs-lookup"><span data-stu-id="c8cf6-102">Storing Ink</span></span>
<span data-ttu-id="c8cf6-103"><xref:System.Windows.Ink.StrokeCollection.Save%2A>メソッドは、インクとして形式 ISF (Ink Serialized) を格納するためのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-103">The <xref:System.Windows.Ink.StrokeCollection.Save%2A> methods provide support for storing ink as Ink Serialized Format (ISF).</span></span> <span data-ttu-id="c8cf6-104">コンス トラクター、<xref:System.Windows.Ink.StrokeCollection>クラスは、インク データを読み取るためのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-104">Constructors for the <xref:System.Windows.Ink.StrokeCollection> class provide support for reading ink data.</span></span>  
  
## <a name="ink-storage-and-retrieval"></a><span data-ttu-id="c8cf6-105">インクの格納と取得</span><span class="sxs-lookup"><span data-stu-id="c8cf6-105">Ink Storage and Retrieval</span></span>  
 <span data-ttu-id="c8cf6-106">このセクションが格納およびのインクを取得する方法について説明します、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-106">This section discusses how to store and retrieve ink in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] platform.</span></span>  
  
 <span data-ttu-id="c8cf6-107">次の例では、ファイルの保存のダイアログ ボックスをユーザーに提示しからインクを保存するボタンのクリック イベント ハンドラーの実装、<xref:System.Windows.Controls.InkCanvas>ファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-107">The following example implements a button-click event handler that presents the user with a File Save dialog box and saves the ink from an <xref:System.Windows.Controls.InkCanvas> out to a file.</span></span>  
  
 [!code-csharp[DigitalInkTopics#12](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 <span data-ttu-id="c8cf6-108">次の例では、ファイルを開く ダイアログ ボックスをユーザーに提示し、ファイルからインクを読み取る ボタンのクリック イベント ハンドラーの実装、<xref:System.Windows.Controls.InkCanvas>要素。</span><span class="sxs-lookup"><span data-stu-id="c8cf6-108">The following example implements a button-click event handler that presents the user with a File Open dialog box and reads ink from the file into an <xref:System.Windows.Controls.InkCanvas> element.</span></span>  
  
 [!code-csharp[DigitalInkTopics#13](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="c8cf6-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8cf6-109">See also</span></span>

- <xref:System.Windows.Controls.InkCanvas>
- [<span data-ttu-id="c8cf6-110">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="c8cf6-110">Windows Presentation Foundation</span></span>](../index.md)
