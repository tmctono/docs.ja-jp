---
title: '方法: アニメーションを使用してメディアを再生する'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 200f9d62c67a02088fe5a5789cdb41a04837d430
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921668"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="88d97-102">方法: アニメーションを使用してメディアを再生する</span><span class="sxs-lookup"><span data-stu-id="88d97-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="88d97-103">この例を使用して、同時にメディアとアニメーションを再生する方法を示しています、<xref:System.Windows.Media.MediaTimeline>と<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>、同じクラス<xref:System.Windows.Media.Animation.Storyboard>します。</span><span class="sxs-lookup"><span data-stu-id="88d97-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88d97-104">例</span><span class="sxs-lookup"><span data-stu-id="88d97-104">Example</span></span>  
 <span data-ttu-id="88d97-105">1 つまたは複数を使用する<xref:System.Windows.Media.MediaTimeline>内のオブジェクトを<xref:System.Windows.Media.Animation.Storyboard>と共に他<xref:System.Windows.Media.Animation.Timeline>アニメーションなどのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="88d97-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="88d97-106">次の例のセット、<xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>のプロパティ、<xref:System.Windows.Media.Animation.Storyboard>の値に`Slip`メディア (この例ではビデオ) が進行するまで、アニメーションが進行しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="88d97-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="88d97-107">この機能は、読み込み時間のためにメディアの再生が遅れる場合などに必要です。</span><span class="sxs-lookup"><span data-stu-id="88d97-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="88d97-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="88d97-108">See also</span></span>

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="88d97-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="88d97-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="88d97-110">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="88d97-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="88d97-111">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="88d97-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="88d97-112">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="88d97-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="88d97-113">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="88d97-113">Graphics and Multimedia</span></span>](index.md)
