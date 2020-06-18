---
title: ClearType レジストリの設定
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: bedd99fcf9b4ca1d10b4c24d7cff9de320e6fd12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186176"
---
# <a name="cleartype-registry-settings"></a><span data-ttu-id="a17f6-102">ClearType レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="a17f6-102">ClearType Registry Settings</span></span>
<span data-ttu-id="a17f6-103">このトピックでは、WPF アプリケーションで使用される Microsoft ClearType のレジストリ設定の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-103">This topic provides an overview of the Microsoft ClearType registry settings that are used by WPF applications.</span></span>  

<a name="overview"></a>
## <a name="technology-overview"></a><span data-ttu-id="a17f6-104">テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="a17f6-104">Technology Overview</span></span>  
 <span data-ttu-id="a17f6-105">ディスプレイ デバイスにテキストをレンダリングする [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションでは、ClearType 機能を使用してレンダリング エクスペリエンスが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-105">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications that render text to a display device use ClearType features to provide an enhanced reading experience.</span></span> <span data-ttu-id="a17f6-106">ClearType は、ラップトップや Pocket PC の画面、フラット パネル モニターなど、既存の LCD (液晶ディスプレイ) でのテキストの読みやすさを向上させるために Microsoft によって開発されたソフトウェア テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="a17f6-106">ClearType is a software technology developed by Microsoft that improves the readability of text on existing LCDs (Liquid Crystal Displays), such as laptop screens, Pocket PC screens and flat panel monitors.</span></span> <span data-ttu-id="a17f6-107">ClearType は、LCD 画面の各ピクセル内の個々の垂直カラー ストライプ要素にアクセスすることによって機能します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-107">ClearType works by accessing the individual vertical color stripe elements in every pixel of an LCD screen.</span></span> <span data-ttu-id="a17f6-108">ClearType の詳細については、「[ClearType の概要](cleartype-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a17f6-108">For more information on ClearType, see [ClearType Overview](cleartype-overview.md).</span></span>  
  
 <span data-ttu-id="a17f6-109">ClearType でレンダリングされるテキストの表示は、表示先のディスプレイ デバイスによって大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-109">Text that is rendered with ClearType can appear significantly different when viewed on various display devices.</span></span> <span data-ttu-id="a17f6-110">たとえば、一般的な赤、緑、青 (RGB) の順ではなく青、緑、赤の順でカラー ストライプ要素を実装するモニターもわずかに存在します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-110">For example, a small number of monitors implement the color stripe elements in blue, green, red order rather than the more common red, green, blue (RGB) order.</span></span>  
  
 <span data-ttu-id="a17f6-111">また、ClearType でレンダリングされるテキストの表示は、各個人の色の感度レベルによっても大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-111">Text that is rendered with ClearType can also appear significantly different when viewed by individuals with varying levels of color sensitivity.</span></span> <span data-ttu-id="a17f6-112">他の人よりも色のわずかな違いを見分ける能力に長けている人もいます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-112">Some individuals can detect slight differences in color better than others.</span></span>  
  
 <span data-ttu-id="a17f6-113">それぞれの場合において、各個人が最も読みやすい表示を実現するために、ClearType 機能を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-113">In each of these cases, ClearType features need to be modified in order to provide the best reading experience for each individual.</span></span>  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a><span data-ttu-id="a17f6-114">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="a17f6-114">Registry Settings</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="a17f6-115">では、ClearType の機能を制御するために、4 つのレジストリ設定が指定されています。</span><span class="sxs-lookup"><span data-stu-id="a17f6-115">specifies four registry settings for controlling ClearType features:</span></span>  
  
|<span data-ttu-id="a17f6-116">設定</span><span class="sxs-lookup"><span data-stu-id="a17f6-116">Setting</span></span>|<span data-ttu-id="a17f6-117">説明</span><span class="sxs-lookup"><span data-stu-id="a17f6-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a17f6-118">ClearType レベル</span><span class="sxs-lookup"><span data-stu-id="a17f6-118">ClearType level</span></span>|<span data-ttu-id="a17f6-119">ClearType の色の鮮明度を示します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-119">Describes the level of ClearType color clarity.</span></span>|  
|<span data-ttu-id="a17f6-120">ガンマ レベル</span><span class="sxs-lookup"><span data-stu-id="a17f6-120">Gamma level</span></span>|<span data-ttu-id="a17f6-121">ディスプレイ デバイスのピクセル カラー コンポーネントのレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-121">Describes the level of the pixel color component for a display device.</span></span>|  
|<span data-ttu-id="a17f6-122">ピクセル構造</span><span class="sxs-lookup"><span data-stu-id="a17f6-122">Pixel structure</span></span>|<span data-ttu-id="a17f6-123">ディスプレイ デバイスのピクセルの配置を示します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-123">Describes the arrangement of pixels for a display device.</span></span>|  
|<span data-ttu-id="a17f6-124">テキストのコントラスト レベル</span><span class="sxs-lookup"><span data-stu-id="a17f6-124">Text contrast level</span></span>|<span data-ttu-id="a17f6-125">表示されるテキストのコントラストのレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-125">Describes the level of contrast for displayed text.</span></span>|  
  
 <span data-ttu-id="a17f6-126">これらの設定には、所定の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の ClearType レジストリ設定の参照方法を認識している外部構成ユーティリティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-126">These settings can be accessed by an external configuration utility that knows how to reference the identified [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType registry settings.</span></span> <span data-ttu-id="a17f6-127">これらの設定は、Windows レジストリ エディターを使用して値に直接アクセスして作成または変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-127">These settings can also be created or modified by accessing the values directly by using the Windows Registry Editor.</span></span>  
  
 <span data-ttu-id="a17f6-128">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType レジストリ設定が設定されていない場合 (既定の状態)、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションは Windows のシステム パラメーター情報でフォント スムージングの設定を照会します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-128">If the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType registry settings are not set (which is the default state), the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application queries the Windows system parameters information for font smoothing settings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a17f6-129">ディスプレイ デバイス名の列挙については、`SystemParametersInfo` Win32 関数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a17f6-129">For information on enumerating display device names, see the `SystemParametersInfo`Win32 function.</span></span>  
  
<a name="ClearType_level"></a>
## <a name="cleartype-level"></a><span data-ttu-id="a17f6-130">ClearType レベル</span><span class="sxs-lookup"><span data-stu-id="a17f6-130">ClearType Level</span></span>  
 <span data-ttu-id="a17f6-131">ClearType レベルを設定すると、個人の色の感度および知覚に基づいてテキストのレンダリングを調整できます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-131">The ClearType level allows you to adjust the rendering of text based on the color sensitivity and perception of an individual.</span></span> <span data-ttu-id="a17f6-132">人によっては、最高レベルの ClearType を使用するテキストのレンダリングでは最も読みやすい表示が実現されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-132">For some individuals, the rendering of text that uses ClearType at its highest level does not produce the best reading experience.</span></span>  
  
 <span data-ttu-id="a17f6-133">ClearType レベルは、0 から 100 の範囲の整数値です。</span><span class="sxs-lookup"><span data-stu-id="a17f6-133">The ClearType level is an integer value that ranges from 0 to 100.</span></span> <span data-ttu-id="a17f6-134">既定のレベルは 100 です。これは、ClearType でディスプレイ デバイスの最大限のカラー ストライプ要素が使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-134">The default level is 100, which means ClearType uses the maximum capability of the color stripe elements of the display device.</span></span> <span data-ttu-id="a17f6-135">ただし、ClearType レベルが 0 の場合、テキストはグレースケールでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-135">However, a ClearType level of 0 renders text as gray scale.</span></span> <span data-ttu-id="a17f6-136">ClearType レベルを 0 から 100 の間に設定することで、個人の色の感度に適した中間レベルを実現できます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-136">By setting the ClearType level somewhere between 0 and 100, you can create an intermediate level that is suitable to an individual's color sensitivity.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="a17f6-137">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="a17f6-137">Registry Setting</span></span>  
 <span data-ttu-id="a17f6-138">ClearType レベルのレジストリ設定は、特定のディスプレイ デバイス名に対応する個々のユーザー設定の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-138">The registry setting location for the ClearType level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="a17f6-139">ユーザーのディスプレイ デバイス名ごとに `ClearTypeLevel` の DWORD 値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-139">For each display device name for a user, a `ClearTypeLevel` DWORD value is defined.</span></span> <span data-ttu-id="a17f6-140">次のスクリーンショットは、ClearType レベルのレジストリ エディターの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="a17f6-140">The following screenshot shows the Registry Editor setting for the ClearType level.</span></span>  
  
 ![レジストリ エディターでの ClearType の設定。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="a17f6-142">アプリケーションでは、ClearType を使用する場合と使用しない場合のいずれかのモードでテキストがレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-142">applications render text in one of either two modes, with and without ClearType.</span></span> <span data-ttu-id="a17f6-143">ClearType を使用しないテキストのレンダリングは、グレースケール レンダリングと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-143">When text is rendered without ClearType, it is referred to as gray scale rendering.</span></span>  
  
<a name="gamma_level"></a>
## <a name="gamma-level"></a><span data-ttu-id="a17f6-144">ガンマ レベル</span><span class="sxs-lookup"><span data-stu-id="a17f6-144">Gamma Level</span></span>  
 <span data-ttu-id="a17f6-145">ガンマ レベルとは、ピクセル値と輝度間の非線形リレーションシップのことです。</span><span class="sxs-lookup"><span data-stu-id="a17f6-145">The gamma level refers to the nonlinear relationship between a pixel value and luminance.</span></span> <span data-ttu-id="a17f6-146">ガンマ レベル設定は、ディスプレイ デバイスの物理特性に対応する必要があります。対応していない場合、レンダリング出力にゆがみが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-146">The gamma level setting should correspond to the physical characteristics of the display device; otherwise, distortions in rendered output may occur.</span></span> <span data-ttu-id="a17f6-147">たとえば、テキストの表示が広すぎたり狭すぎたりする場合や、色縁がグリフの縦線の端に表示される場合などがあります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-147">For example, text may appear too wide or too narrow, or color fringes may appear on the edges of vertical stems of glyphs.</span></span>  
  
 <span data-ttu-id="a17f6-148">ガンマ レベルは、1000 から 2200 の範囲の整数値です。</span><span class="sxs-lookup"><span data-stu-id="a17f6-148">The gamma level is an integer value that ranges from 1000 to 2200.</span></span> <span data-ttu-id="a17f6-149">既定のレベルは 1900 です。</span><span class="sxs-lookup"><span data-stu-id="a17f6-149">The default level is 1900.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="a17f6-150">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="a17f6-150">Registry Setting</span></span>  
 <span data-ttu-id="a17f6-151">ガンマ レベルのレジストリ設定は、特定のディスプレイ デバイス名に対応するローカル マシン設定の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-151">The registry setting location for the gamma level is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="a17f6-152">ユーザーのディスプレイ デバイス名ごとに `GammaLevel` の DWORD 値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-152">For each display device name for a user, a `GammaLevel` DWORD value is defined.</span></span> <span data-ttu-id="a17f6-153">次のスクリーンショットは、ガンマ レベルのレジストリ エディターの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="a17f6-153">The following screenshot shows the Registry Editor setting for the gamma level.</span></span>  
  
 ![レジストリ エディターでの ClearType のガンマ レベルの設定](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>
## <a name="pixel-structure"></a><span data-ttu-id="a17f6-155">ピクセル構造</span><span class="sxs-lookup"><span data-stu-id="a17f6-155">Pixel Structure</span></span>  
 <span data-ttu-id="a17f6-156">ピクセル構造は、ディスプレイ デバイスを構成するピクセルの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-156">The pixel structure describes the type of pixels that make up a display device.</span></span> <span data-ttu-id="a17f6-157">ピクセル構造は、次の 3 種類のいずれかとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-157">The pixel structure is defined as one of three types:</span></span>  
  
|<span data-ttu-id="a17f6-158">種類</span><span class="sxs-lookup"><span data-stu-id="a17f6-158">Type</span></span>|<span data-ttu-id="a17f6-159">[値]</span><span class="sxs-lookup"><span data-stu-id="a17f6-159">Value</span></span>|<span data-ttu-id="a17f6-160">説明</span><span class="sxs-lookup"><span data-stu-id="a17f6-160">Description</span></span>|  
|----------|-----------|-----------------|  
|<span data-ttu-id="a17f6-161">フラット</span><span class="sxs-lookup"><span data-stu-id="a17f6-161">Flat</span></span>|<span data-ttu-id="a17f6-162">0</span><span class="sxs-lookup"><span data-stu-id="a17f6-162">0</span></span>|<span data-ttu-id="a17f6-163">ディスプレイ デバイスにピクセル構造がありません。</span><span class="sxs-lookup"><span data-stu-id="a17f6-163">The display device has no pixel structure.</span></span> <span data-ttu-id="a17f6-164">つまり、各色の光源がピクセル領域に均等に拡散しています。これは、グレースケール レンダリングと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-164">This means that light sources for each color are spread equally on the pixel area—this is referred to as gray scale rendering.</span></span> <span data-ttu-id="a17f6-165">標準のディスプレイ デバイスはこのようにして機能します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-165">This is how a standard display device works.</span></span> <span data-ttu-id="a17f6-166">ClearType はレンダリングされたテキストには適用されません。</span><span class="sxs-lookup"><span data-stu-id="a17f6-166">ClearType is never applied to the rendered text.</span></span>|  
|<span data-ttu-id="a17f6-167">RGB</span><span class="sxs-lookup"><span data-stu-id="a17f6-167">RGB</span></span>|<span data-ttu-id="a17f6-168">1</span><span class="sxs-lookup"><span data-stu-id="a17f6-168">1</span></span>|<span data-ttu-id="a17f6-169">ディスプレイ デバイスのピクセルは、赤、緑、青の順の 3 つのストライプで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-169">The display device has pixels that consist of three stripes in the following order: red, green, and blue.</span></span> <span data-ttu-id="a17f6-170">ClearType はレンダリングされたテキストに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-170">ClearType is applied to the rendered text.</span></span>|  
|<span data-ttu-id="a17f6-171">BGR</span><span class="sxs-lookup"><span data-stu-id="a17f6-171">BGR</span></span>|<span data-ttu-id="a17f6-172">2</span><span class="sxs-lookup"><span data-stu-id="a17f6-172">2</span></span>|<span data-ttu-id="a17f6-173">ディスプレイ デバイスのピクセルは、青、緑、赤の順の 3 つのストライプで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-173">The display device has pixels that consist of three stripes in the following order: blue, green, and red.</span></span> <span data-ttu-id="a17f6-174">ClearType はレンダリングされたテキストに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-174">ClearType is applied to the rendered text.</span></span> <span data-ttu-id="a17f6-175">順序が RGB の場合の逆であることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="a17f6-175">Notice how the order is inverted from the RGB type.</span></span>|  
  
 <span data-ttu-id="a17f6-176">ピクセル構造は、0 から 2 の範囲の整数値に対応します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-176">The pixel structure corresponds to an integer value that ranges from 0 to 2.</span></span> <span data-ttu-id="a17f6-177">既定のレベルは 0 です。これは、フラット ピクセル構造を表します。</span><span class="sxs-lookup"><span data-stu-id="a17f6-177">The default level is 0, which represents a flat pixel structure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a17f6-178">ディスプレイ デバイス名の列挙については、`EnumDisplayDevices` Win32 関数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a17f6-178">For information on enumerating display device names, see the `EnumDisplayDevices`Win32 function.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="a17f6-179">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="a17f6-179">Registry Setting</span></span>  
 <span data-ttu-id="a17f6-180">ピクセル構造のレジストリ設定は、特定のディスプレイ デバイス名に対応するローカル マシン設定の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-180">The registry setting location for the pixel structure is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="a17f6-181">ユーザーのディスプレイ デバイス名ごとに `PixelStructure` の DWORD 値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-181">For each display device name for a user, a `PixelStructure` DWORD value is defined.</span></span> <span data-ttu-id="a17f6-182">次のスクリーンショットは、ピクセル構造のレジストリ エディターの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="a17f6-182">The following screenshot shows the Registry Editor setting for the pixel structure.</span></span>  
  
 ![レジストリ エディターでの ClearType のガンマ レベルの設定](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>
## <a name="text-contrast-level"></a><span data-ttu-id="a17f6-184">テキストのコントラスト レベル</span><span class="sxs-lookup"><span data-stu-id="a17f6-184">Text Contrast Level</span></span>  
 <span data-ttu-id="a17f6-185">テキストのコントラスト レベルを設定すると、グリフの縦線の幅に基づいてテキストのレンダリングを調整できます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-185">The text contrast level allows you to adjust the rendering of text based on the stem widths of glyphs.</span></span> <span data-ttu-id="a17f6-186">テキストのコントラスト レベルは 0 から 6 の範囲の整数値です。整数値を大きくすると、縦線の幅が広くなります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-186">The text contrast level is an integer value that ranges from 0 to 6—the larger the integer value, the wider the stem.</span></span> <span data-ttu-id="a17f6-187">既定のレベルは 1 です。</span><span class="sxs-lookup"><span data-stu-id="a17f6-187">The default level is 1.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="a17f6-188">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="a17f6-188">Registry Setting</span></span>  
 <span data-ttu-id="a17f6-189">テキストのコントラスト レベルのレジストリ設定は、特定のディスプレイ デバイス名に対応する個々のユーザー設定の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="a17f6-189">The registry setting location for the text contrast level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="a17f6-190">ユーザーのディスプレイ デバイス名ごとに `TextContrastLevel` の DWORD 値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="a17f6-190">For each display device name for a user, a `TextContrastLevel` DWORD value is defined.</span></span> <span data-ttu-id="a17f6-191">次のスクリーンショットは、テキストのコントラスト レベルのレジストリ エディターの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="a17f6-191">The following screenshot shows the Registry Editor setting for the text contrast level.</span></span>  
  
 ![レジストリ エディターでの ClearType の設定。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a><span data-ttu-id="a17f6-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="a17f6-193">See also</span></span>

- [<span data-ttu-id="a17f6-194">ClearType の概要</span><span class="sxs-lookup"><span data-stu-id="a17f6-194">ClearType Overview</span></span>](cleartype-overview.md)
- [<span data-ttu-id="a17f6-195">ClearType アンチエイリアシング</span><span class="sxs-lookup"><span data-stu-id="a17f6-195">ClearType Antialiasing</span></span>](/windows/desktop/gdi/cleartype-antialiasing)
