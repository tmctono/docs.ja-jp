---
title: '方法: メディアの再生を反復する'
ms.date: 03/30/2017
helpviewer_keywords:
- media [WPF], repeating playback
- repeating media playback [WPF]
- multimedia [WPF], repeating media playback
- playback of media [WPF], repeating
ms.assetid: 02ab486d-c6b6-4918-9edd-45a12aca4683
ms.openlocfilehash: b6df627d8837751a26b48725c25aab8d457caf36
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371053"
---
# <a name="how-to-repeat-media-playback"></a><span data-ttu-id="dc9a0-102">方法: メディアの再生を反復する</span><span class="sxs-lookup"><span data-stu-id="dc9a0-102">How to: Repeat Media Playback</span></span>
<span data-ttu-id="dc9a0-103">この例では、メディアを無制限に再生する (無限ループで再生されるようにメディアを設定する) 方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dc9a0-103">This example shows how to playback media indefinitely, that is, to set media so that it plays in an infinite loop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc9a0-104">例</span><span class="sxs-lookup"><span data-stu-id="dc9a0-104">Example</span></span>  
 <span data-ttu-id="dc9a0-105">次の例では<xref:System.Windows.Controls.MediaElement>と<xref:System.Windows.Media.MediaTimeline>で、<xref:System.Windows.Media.Animation.Storyboard>無限ループにメディア クリップを再生します。</span><span class="sxs-lookup"><span data-stu-id="dc9a0-105">The following example uses <xref:System.Windows.Controls.MediaElement> and <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to play a media clip in an infinite loop.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#SoundRepeatExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundRepeatExample.xaml#soundrepeatexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="dc9a0-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc9a0-106">See also</span></span>
- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="dc9a0-107">方法トピック</span><span class="sxs-lookup"><span data-stu-id="dc9a0-107">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="dc9a0-108">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="dc9a0-108">Graphics and Multimedia</span></span>](index.md)
