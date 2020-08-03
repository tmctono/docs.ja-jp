---
title: '軽減策: WPF レイアウト'
description: 1 ピクセル単位で動かすことでオブジェクトを配置するなど、WPF コントロール レイアウトを変更した結果として発生する問題を軽減する方法について説明します。
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: e4e4612f7b39eefbf0e76ac86c8eb644c257ba75
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475347"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="d6bf5-103">軽減策:WPF レイアウト</span><span class="sxs-lookup"><span data-stu-id="d6bf5-103">Mitigation: WPF Layout</span></span>
<span data-ttu-id="d6bf5-104">WPF コントロールのレイアウトが若干変化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6bf5-104">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="d6bf5-105">影響</span><span class="sxs-lookup"><span data-stu-id="d6bf5-105">Impact</span></span>  
 <span data-ttu-id="d6bf5-106">この変更の結果、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="d6bf5-106">As a result of this change:</span></span>  
  
- <span data-ttu-id="d6bf5-107">要素の幅または高さが最大で 1 ピクセル拡大または縮小することがあります。</span><span class="sxs-lookup"><span data-stu-id="d6bf5-107">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="d6bf5-108">オブジェクトの配置が最大で 1 ピクセル移動することがあります。</span><span class="sxs-lookup"><span data-stu-id="d6bf5-108">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="d6bf5-109">中央揃えの要素が中央から最大で 1 ピクセル垂直まは水平方向にずれることがあります。</span><span class="sxs-lookup"><span data-stu-id="d6bf5-109">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="d6bf5-110">既定では、この新しいレイアウトは .NET Framework の 4.6 を対象とするアプリに対してのみ有効となります。</span><span class="sxs-lookup"><span data-stu-id="d6bf5-110">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="d6bf5-111">軽減策</span><span class="sxs-lookup"><span data-stu-id="d6bf5-111">Mitigation</span></span>  
 <span data-ttu-id="d6bf5-112">この変更では、DPI が高いときにWPF コントロールの一番右または一番下でクリッピングの発生を除去する傾向があるため、app.config ファイルの `<runtime>` セクションに次の行を追加することによって、以前のバージョンの .NET Framework を対象としながら .NET Framework 4.6 上で実行されているアプリがこの新しい動作を選択ことができます。</span><span class="sxs-lookup"><span data-stu-id="d6bf5-112">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="d6bf5-113">.NET Framework 4.6 を対象としながら以前のレイアウト アルゴリズムを使用して WPF コントロールをレンダリングする必要があるアプリの場合、app.config ファイルの `<runtime>` セクションに次の行を追加することによってそれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d6bf5-113">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6bf5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6bf5-114">See also</span></span>

- [<span data-ttu-id="d6bf5-115">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="d6bf5-115">Application compatibility</span></span>](application-compatibility.md)
