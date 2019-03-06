---
title: '方法: ストーリーボードを同期的にシークする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- seeking Storyboards synchronously [WPF]
- Storyboards [WPF], seeking synchronously
ms.assetid: 03e06271-a946-4810-88ea-3fb4cfa9e0f1
ms.openlocfilehash: 8ac55346ac83ee94318de90655bde6053ef20687
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371321"
---
# <a name="how-to-seek-a-storyboard-synchronously"></a><span data-ttu-id="748ab-102">方法: ストーリーボードを同期的にシークする</span><span class="sxs-lookup"><span data-stu-id="748ab-102">How to: Seek a Storyboard Synchronously</span></span>
<span data-ttu-id="748ab-103">次の例は、使用する方法を示します、<xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>のメソッドを<xref:System.Windows.Media.Animation.Storyboard>を同期的に、ストーリー ボード アニメーションの任意の位置をシークします。</span><span class="sxs-lookup"><span data-stu-id="748ab-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to seek to any position in a storyboard animation synchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="748ab-104">例</span><span class="sxs-lookup"><span data-stu-id="748ab-104">Example</span></span>  
 <span data-ttu-id="748ab-105">サンプルの XAML マークアップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="748ab-105">The following is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardSynchronouslyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml#seekstoryboardsynchronouslyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="748ab-106">例</span><span class="sxs-lookup"><span data-stu-id="748ab-106">Example</span></span>  
 <span data-ttu-id="748ab-107">上記の XAML コードと共に使用するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="748ab-107">The following is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml.cs#seekstoryboardsynchronouslycodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardSynchronouslyExample.xaml.vb#seekstoryboardsynchronouslycodebehindexamplewholepage)]
