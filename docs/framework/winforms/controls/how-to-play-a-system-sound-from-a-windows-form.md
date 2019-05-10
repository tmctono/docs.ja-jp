---
title: '方法: Windows フォームからシステム サウンドを再生する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing for system events
- playing sounds [Windows Forms], Windows Forms
- system sounds [Windows Forms], playing from Windows Forms
- playing sounds [Windows Forms], system
- SoundPlayer class [Windows Forms], system sounds
- sounds [Windows Forms], playing
- examples [Windows Forms], sounds
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
ms.openlocfilehash: 765021875767a754e62e3ec11e56487e4de91e93
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602775"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a><span data-ttu-id="8a9d1-102">方法: Windows フォームからシステム サウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="8a9d1-102">How to: Play a System Sound from a Windows Form</span></span>
<span data-ttu-id="8a9d1-103">実行時に `Exclamation` システム サウンドを再生するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8a9d1-103">The following code example plays the `Exclamation` system sound at run time.</span></span> <span data-ttu-id="8a9d1-104">システムが出す音の詳細については、次を参照してください。<xref:System.Media.SystemSounds>します。</span><span class="sxs-lookup"><span data-stu-id="8a9d1-104">For more information about system sounds, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a9d1-105">例</span><span class="sxs-lookup"><span data-stu-id="8a9d1-105">Example</span></span>  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8a9d1-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8a9d1-106">Compiling the Code</span></span>  
 <span data-ttu-id="8a9d1-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a9d1-107">This example requires:</span></span>  
  
- <span data-ttu-id="8a9d1-108"><xref:System.Media?displayProperty=nameWithType> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="8a9d1-108">A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a9d1-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a9d1-109">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
- [<span data-ttu-id="8a9d1-110">方法: Windows フォームからビープ音を再生します。</span><span class="sxs-lookup"><span data-stu-id="8a9d1-110">How to: Play a Beep from a Windows Form</span></span>](how-to-play-a-beep-from-a-windows-form.md)
- [<span data-ttu-id="8a9d1-111">方法: Windows フォームからサウンドを再生します。</span><span class="sxs-lookup"><span data-stu-id="8a9d1-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
