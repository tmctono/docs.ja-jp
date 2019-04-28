---
title: '方法: BitmapSource オブジェクトをチェーンする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BitmapSource objects [WPF], chaining
- graphics [WPF], chaining BitmapSource objects
- chaining BitmapSource objects [WPF]
ms.assetid: 32d88853-395b-4855-9685-51a482a3b421
ms.openlocfilehash: 403a2a8683e65fd71df89befd59744ac3fe6200c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785659"
---
# <a name="how-to-chain-bitmapsource-objects-together"></a><span data-ttu-id="b0a15-102">方法: BitmapSource オブジェクトをチェーンする</span><span class="sxs-lookup"><span data-stu-id="b0a15-102">How to: Chain BitmapSource Objects Together</span></span>
<span data-ttu-id="b0a15-103">この例では連鎖させることにより、イメージ ソースにさまざまな効果を適用する方法複数<xref:System.Windows.Media.Imaging.BitmapSource>派生オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b0a15-103">This example shows how you can apply a variety of effects to an image source by chaining multiple <xref:System.Windows.Media.Imaging.BitmapSource> derived objects together.</span></span>  
  
 <span data-ttu-id="b0a15-104">次の例では、チェーンを使用して、イメージのソースを反転してピクセル形式を変更します。</span><span class="sxs-lookup"><span data-stu-id="b0a15-104">The following example uses chaining to flip and change the pixel format of the source of an image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0a15-105">例</span><span class="sxs-lookup"><span data-stu-id="b0a15-105">Example</span></span>  
 [!code-xaml[ImagingSnippetGallery_snip#ChainedBitmapSourcesXamlExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_snip/CS/ChainedBitmapSourcesExample.xaml#chainedbitmapsourcesxamlexamplewholepage)]  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/ChainedBitmapSourcesExample.cs#chainedbitmapsourcescodeexamplewholepage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/ChainedBitmapSourcesExample.vb#chainedbitmapsourcescodeexamplewholepage)]
