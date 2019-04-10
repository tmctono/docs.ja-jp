---
title: SoundPlayer クラスの概要
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 3ff23cbfa78b803d4526e7a7c389fd5d458a967c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195008"
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="0e287-102">SoundPlayer クラスの概要</span><span class="sxs-lookup"><span data-stu-id="0e287-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="0e287-103"><xref:System.Media.SoundPlayer> クラスを使用すると、アプリケーションにサウンドを簡単に組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="0e287-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="0e287-104"><xref:System.Media.SoundPlayer>クラスは、リソースまたは UNC や HTTP の場所からの .wav 形式のサウンド ファイルを再生できます。</span><span class="sxs-lookup"><span data-stu-id="0e287-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="0e287-105">さらに、<xref:System.Media.SoundPlayer>クラスでは、読み込みまたは非同期的にサウンドを再生することができます。</span><span class="sxs-lookup"><span data-stu-id="0e287-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="0e287-106"><xref:System.Media.SystemSounds> クラスを使用して、ビープ音を含む、共通のシステム サウンドを再生することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e287-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="0e287-107">一般的に使用されるプロパティ、メソッド、およびイベント</span><span class="sxs-lookup"><span data-stu-id="0e287-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="0e287-108">名前</span><span class="sxs-lookup"><span data-stu-id="0e287-108">Name</span></span>|<span data-ttu-id="0e287-109">説明</span><span class="sxs-lookup"><span data-stu-id="0e287-109">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> <span data-ttu-id="0e287-110">property</span><span class="sxs-lookup"><span data-stu-id="0e287-110">property</span></span>|<span data-ttu-id="0e287-111">サウンドのファイル パスまたは Web アドレスです。</span><span class="sxs-lookup"><span data-stu-id="0e287-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="0e287-112">使用可能な値には UNC または HTTP があります。</span><span class="sxs-lookup"><span data-stu-id="0e287-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> <span data-ttu-id="0e287-113">property</span><span class="sxs-lookup"><span data-stu-id="0e287-113">property</span></span>|<span data-ttu-id="0e287-114">プログラムが、例外をスローする前にサウンドの読み込みを待機するミリ秒単位の時間です。</span><span class="sxs-lookup"><span data-stu-id="0e287-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="0e287-115">既定値は 10 秒です。</span><span class="sxs-lookup"><span data-stu-id="0e287-115">The default is 10 seconds.</span></span>|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> <span data-ttu-id="0e287-116">property</span><span class="sxs-lookup"><span data-stu-id="0e287-116">property</span></span>|<span data-ttu-id="0e287-117">サウンドの読み込みが終了したかどうかを示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="0e287-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<xref:System.Media.SoundPlayer.Load%2A> <span data-ttu-id="0e287-118">メソッド</span><span class="sxs-lookup"><span data-stu-id="0e287-118">method</span></span>|<span data-ttu-id="0e287-119">サウンドを同期的に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0e287-119">Loads a sound synchronously.</span></span>|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> <span data-ttu-id="0e287-120">メソッド</span><span class="sxs-lookup"><span data-stu-id="0e287-120">method</span></span>|<span data-ttu-id="0e287-121">サウンドの非同期的な読み込みを開始します。</span><span class="sxs-lookup"><span data-stu-id="0e287-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="0e287-122">読み込みが完了したら、生成、<xref:System.Media.SoundPlayer.OnLoadCompleted%2A>イベント。</span><span class="sxs-lookup"><span data-stu-id="0e287-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<xref:System.Media.SoundPlayer.Play%2A> <span data-ttu-id="0e287-123">メソッド</span><span class="sxs-lookup"><span data-stu-id="0e287-123">method</span></span>|<span data-ttu-id="0e287-124">指定されたサウンドを再生、<xref:System.Media.SoundPlayer.SoundLocation%2A>または<xref:System.Media.SoundPlayer.Stream%2A>新しいスレッドのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="0e287-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> <span data-ttu-id="0e287-125">メソッド</span><span class="sxs-lookup"><span data-stu-id="0e287-125">method</span></span>|<span data-ttu-id="0e287-126">指定されたサウンドを再生、<xref:System.Media.SoundPlayer.SoundLocation%2A>または<xref:System.Media.SoundPlayer.Stream%2A>プロパティ、現在のスレッドにします。</span><span class="sxs-lookup"><span data-stu-id="0e287-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<xref:System.Media.SoundPlayer.Stop%2A> <span data-ttu-id="0e287-127">メソッド</span><span class="sxs-lookup"><span data-stu-id="0e287-127">method</span></span>|<span data-ttu-id="0e287-128">現在再生されているサウンドを停止します。</span><span class="sxs-lookup"><span data-stu-id="0e287-128">Stops any sound currently playing.</span></span>|  
|<xref:System.Media.SoundPlayer.LoadCompleted> <span data-ttu-id="0e287-129">event</span><span class="sxs-lookup"><span data-stu-id="0e287-129">event</span></span>|<span data-ttu-id="0e287-130">サウンドの読み込みが試みられた後に発生します。</span><span class="sxs-lookup"><span data-stu-id="0e287-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e287-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e287-131">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
