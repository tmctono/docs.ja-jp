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
ms.openlocfilehash: d85d8cd40ff2b32cb3f2a79cf9a8221964f186c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153232"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a><span data-ttu-id="c6bf0-102">方法: Windows フォームからシステム サウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="c6bf0-102">How to: Play a System Sound from a Windows Form</span></span>
<span data-ttu-id="c6bf0-103">実行時に `Exclamation` システム サウンドを再生するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c6bf0-103">The following code example plays the `Exclamation` system sound at run time.</span></span> <span data-ttu-id="c6bf0-104">システムが出す音の詳細については、次を参照してください。<xref:System.Media.SystemSounds>します。</span><span class="sxs-lookup"><span data-stu-id="c6bf0-104">For more information about system sounds, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6bf0-105">例</span><span class="sxs-lookup"><span data-stu-id="c6bf0-105">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="c6bf0-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c6bf0-106">Compiling the Code</span></span>  
 <span data-ttu-id="c6bf0-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c6bf0-107">This example requires:</span></span>  
  
-   <span data-ttu-id="c6bf0-108"><xref:System.Media?displayProperty=nameWithType> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="c6bf0-108">A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6bf0-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6bf0-109">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
- [<span data-ttu-id="c6bf0-110">方法: Windows フォームからビープ音を再生する</span><span class="sxs-lookup"><span data-stu-id="c6bf0-110">How to: Play a Beep from a Windows Form</span></span>](how-to-play-a-beep-from-a-windows-form.md)
- [<span data-ttu-id="c6bf0-111">方法: Windows フォームからサウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="c6bf0-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
