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
ms.openlocfilehash: 0aa01f600873dd8853e1c33d5443448835e11455
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146225"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="a344a-102">方法: Windows フォームからビープ音を再生する</span><span class="sxs-lookup"><span data-stu-id="a344a-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="a344a-103">実行時にビープ音を再生する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a344a-103">This example plays a beep at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a344a-104">例</span><span class="sxs-lookup"><span data-stu-id="a344a-104">Example</span></span>  
  
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
>  <span data-ttu-id="a344a-105">再生されるサウンド、C#コード サンプルはによって決定されます、<xref:System.Media.SystemSounds.Beep%2A>システム サウンド設定します。</span><span class="sxs-lookup"><span data-stu-id="a344a-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="a344a-106">詳細については、「 <xref:System.Media.SystemSounds> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a344a-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a344a-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a344a-107">Compiling the Code</span></span>  
 <span data-ttu-id="a344a-108">C#、この例への参照が必要です、<xref:System.Media?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="a344a-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a344a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a344a-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="a344a-110">方法: Windows フォームからシステム サウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="a344a-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="a344a-111">方法: Windows フォームからサウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="a344a-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
