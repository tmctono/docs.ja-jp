---
title: '方法: ユーザー イベントによってメディアの再生をトリガーする'
ms.date: 03/30/2017
helpviewer_keywords:
- synchronizing media playback with events [WPF]
- playback of media [WPF], synchronizing with events
- media [WPF], synchronizing playback with events
- multimedia [WPF], synchronizing media playback with events
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
ms.openlocfilehash: 1d71e69bcd0332ba7119977dcf67356a3d79a368
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377977"
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a><span data-ttu-id="42d33-102">方法: ユーザー イベントによってメディアの再生をトリガーする</span><span class="sxs-lookup"><span data-stu-id="42d33-102">How to: Trigger Media Playback with a User Event</span></span>
<span data-ttu-id="42d33-103">この例では、メディアの再生とイベントを同期する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42d33-103">This example shows how to synchronize media playback with an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42d33-104">例</span><span class="sxs-lookup"><span data-stu-id="42d33-104">Example</span></span>  
 <span data-ttu-id="42d33-105">次の例では、<xref:System.Windows.Controls.MediaElement>コントロールと<xref:System.Windows.Media.MediaTimeline>、ユーザーがクリックしたときに発生するサウンドを再生するクラス、<xref:System.Windows.Controls.Button>します。</span><span class="sxs-lookup"><span data-stu-id="42d33-105">The following example uses the <xref:System.Windows.Controls.MediaElement> control and the <xref:System.Windows.Media.MediaTimeline> class to play a sound that occurs when the user clicks a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="42d33-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="42d33-106">See also</span></span>
- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.EventTrigger.RoutedEvent%2A>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="42d33-107">方法トピック</span><span class="sxs-lookup"><span data-stu-id="42d33-107">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="42d33-108">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="42d33-108">Graphics and Multimedia</span></span>](index.md)
