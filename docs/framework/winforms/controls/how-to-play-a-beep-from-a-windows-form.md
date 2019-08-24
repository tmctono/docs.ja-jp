---
title: '方法: Windows フォームからビープ音を再生する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: 7fecc5d5b7259b743926713f87d9303596803582
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015811"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="92006-102">方法: Windows フォームからビープ音を再生する</span><span class="sxs-lookup"><span data-stu-id="92006-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="92006-103">実行時にビープ音を再生する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="92006-103">This example plays a beep at run time.</span></span>

## <a name="example"></a><span data-ttu-id="92006-104">例</span><span class="sxs-lookup"><span data-stu-id="92006-104">Example</span></span>

```vb
Public Sub OnePing()
    Beep()
End Sub
```

```csharp
public void onePing()
{
    SystemSounds.Beep.Play();
}
```

> [!NOTE]
> <span data-ttu-id="92006-105">C#コードサンプルで再生されるサウンドは、 <xref:System.Media.SystemSounds.Beep%2A>システムサウンド設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="92006-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="92006-106">詳細については、「 <xref:System.Media.SystemSounds> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92006-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="92006-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="92006-107">Compiling the Code</span></span>
 <span data-ttu-id="92006-108">のC#場合、この例では<xref:System.Media?displayProperty=nameWithType>名前空間への参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="92006-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="92006-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="92006-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="92006-110">方法: Windows フォームからシステムサウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="92006-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="92006-111">方法: Windows フォームからサウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="92006-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
