---
title: ClearType レジストリの設定
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: 5113de6d8d333983e6e26579ff9803a9f5a62816
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254174"
---
# <a name="cleartype-registry-settings"></a><span data-ttu-id="3f01f-102">ClearType レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="3f01f-102">ClearType Registry Settings</span></span>
<span data-ttu-id="3f01f-103">このトピックでは、WPF アプリケーションで使用される Microsoft ClearType レジストリ設定の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-103">This topic provides an overview of the Microsoft ClearType registry settings that are used by WPF applications.</span></span>  

<a name="overview"></a>   
## <a name="technology-overview"></a><span data-ttu-id="3f01f-104">テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="3f01f-104">Technology Overview</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="3f01f-105">ディスプレイデバイスにテキストを表示するアプリケーションでは、ClearType 機能を使用して読みやすさを向上させます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-105">applications that render text to a display device use ClearType features to provide an enhanced reading experience.</span></span> <span data-ttu-id="3f01f-106">ClearType は、Microsoft によって開発されたソフトウェアテクノロジで、ラップトップの画面、Pocket PC の画面、フラットパネルモニターなど、既存の Lcd (液晶ディスプレイ) でのテキストの読みやすさを向上させます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-106">ClearType is a software technology developed by Microsoft that improves the readability of text on existing LCDs (Liquid Crystal Displays), such as laptop screens, Pocket PC screens and flat panel monitors.</span></span> <span data-ttu-id="3f01f-107">ClearType は、LCD 画面のすべてのピクセルで個々の垂直色のストライプ要素にアクセスすることによって機能します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-107">ClearType works by accessing the individual vertical color stripe elements in every pixel of an LCD screen.</span></span> <span data-ttu-id="3f01f-108">ClearType の詳細については、「 [cleartype の概要](cleartype-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f01f-108">For more information on ClearType, see [ClearType Overview](cleartype-overview.md).</span></span>  
  
 <span data-ttu-id="3f01f-109">ClearType を使用してレンダリングされたテキストは、さまざまなディスプレイデバイスで表示すると、大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-109">Text that is rendered with ClearType can appear significantly different when viewed on various display devices.</span></span> <span data-ttu-id="3f01f-110">たとえば、少数のモニターでは、より一般的な赤、緑、青 (RGB) の順序ではなく、青、緑、赤の順序でカラーストライプ要素が実装されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-110">For example, a small number of monitors implement the color stripe elements in blue, green, red order rather than the more common red, green, blue (RGB) order.</span></span>  
  
 <span data-ttu-id="3f01f-111">ClearType を使用して表示されるテキストは、さまざまな色の区別レベルを持つ個人によって表示される場合に、大幅に異なる表示になることもあります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-111">Text that is rendered with ClearType can also appear significantly different when viewed by individuals with varying levels of color sensitivity.</span></span> <span data-ttu-id="3f01f-112">他の人よりも色のわずかな違いを見分ける能力に長けている人もいます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-112">Some individuals can detect slight differences in color better than others.</span></span>  
  
 <span data-ttu-id="3f01f-113">これらの各ケースでは、各ユーザーに最適な読み取りエクスペリエンスを提供するために、ClearType 機能を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-113">In each of these cases, ClearType features need to be modified in order to provide the best reading experience for each individual.</span></span>  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a><span data-ttu-id="3f01f-114">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="3f01f-114">Registry Settings</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="3f01f-115">ClearType 機能を制御するための4つのレジストリ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-115">specifies four registry settings for controlling ClearType features:</span></span>  
  
|<span data-ttu-id="3f01f-116">設定</span><span class="sxs-lookup"><span data-stu-id="3f01f-116">Setting</span></span>|<span data-ttu-id="3f01f-117">説明</span><span class="sxs-lookup"><span data-stu-id="3f01f-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f01f-118">ClearType レベル</span><span class="sxs-lookup"><span data-stu-id="3f01f-118">ClearType level</span></span>|<span data-ttu-id="3f01f-119">ClearType の色をわかりやすくするレベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-119">Describes the level of ClearType color clarity.</span></span>|  
|<span data-ttu-id="3f01f-120">ガンマ レベル</span><span class="sxs-lookup"><span data-stu-id="3f01f-120">Gamma level</span></span>|<span data-ttu-id="3f01f-121">ディスプレイ デバイスのピクセル カラー コンポーネントのレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-121">Describes the level of the pixel color component for a display device.</span></span>|  
|<span data-ttu-id="3f01f-122">ピクセル構造</span><span class="sxs-lookup"><span data-stu-id="3f01f-122">Pixel structure</span></span>|<span data-ttu-id="3f01f-123">ディスプレイ デバイスのピクセルの配置を示します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-123">Describes the arrangement of pixels for a display device.</span></span>|  
|<span data-ttu-id="3f01f-124">テキストのコントラスト レベル</span><span class="sxs-lookup"><span data-stu-id="3f01f-124">Text contrast level</span></span>|<span data-ttu-id="3f01f-125">表示されるテキストのコントラストのレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-125">Describes the level of contrast for displayed text.</span></span>|  
  
 <span data-ttu-id="3f01f-126">これらの設定には、特定[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]の ClearType レジストリ設定を参照する方法を認識する外部構成ユーティリティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-126">These settings can be accessed by an external configuration utility that knows how to reference the identified [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType registry settings.</span></span> <span data-ttu-id="3f01f-127">これらの設定は、Windows レジストリエディターを使用して値に直接アクセスすることによって作成または変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-127">These settings can also be created or modified by accessing the values directly by using the Windows Registry Editor.</span></span>  
  
 <span data-ttu-id="3f01f-128">ClearType レジストリ設定が設定されていない場合 (既定の状態)、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションは Windows システムパラメーター情報に対してフォントスムージング設定を照会します。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f01f-128">If the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType registry settings are not set (which is the default state), the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application queries the Windows system parameters information for font smoothing settings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f01f-129">表示デバイス名の列挙の詳細について`SystemParametersInfo`は、 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]関数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f01f-129">For information on enumerating display device names, see the `SystemParametersInfo`[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function.</span></span>  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a><span data-ttu-id="3f01f-130">ClearType レベル</span><span class="sxs-lookup"><span data-stu-id="3f01f-130">ClearType Level</span></span>  
 <span data-ttu-id="3f01f-131">ClearType レベルでは、個人の色の区別と認識に基づいてテキストのレンダリングを調整できます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-131">The ClearType level allows you to adjust the rendering of text based on the color sensitivity and perception of an individual.</span></span> <span data-ttu-id="3f01f-132">場合によっては、ClearType を最高レベルで使用するテキストをレンダリングしても、最適な読み取りエクスペリエンスが得られないことがあります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-132">For some individuals, the rendering of text that uses ClearType at its highest level does not produce the best reading experience.</span></span>  
  
 <span data-ttu-id="3f01f-133">ClearType レベルは、0 ~ 100 の範囲の整数値です。</span><span class="sxs-lookup"><span data-stu-id="3f01f-133">The ClearType level is an integer value that ranges from 0 to 100.</span></span> <span data-ttu-id="3f01f-134">既定のレベルは100です。これは、ClearType がディスプレイデバイスのカラーストライプ要素の最大機能を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-134">The default level is 100, which means ClearType uses the maximum capability of the color stripe elements of the display device.</span></span> <span data-ttu-id="3f01f-135">ただし、ClearType レベルが0の場合、テキストはグレースケールとしてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-135">However, a ClearType level of 0 renders text as gray scale.</span></span> <span data-ttu-id="3f01f-136">0 ~ 100 の範囲の ClearType レベルを設定することにより、個人の色の区別に適した中間レベルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-136">By setting the ClearType level somewhere between 0 and 100, you can create an intermediate level that is suitable to an individual's color sensitivity.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="3f01f-137">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="3f01f-137">Registry Setting</span></span>  
 <span data-ttu-id="3f01f-138">ClearType レベルのレジストリ設定の場所は、特定の表示デバイス名に対応する個々のユーザー設定です。</span><span class="sxs-lookup"><span data-stu-id="3f01f-138">The registry setting location for the ClearType level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="3f01f-139">ユーザーの表示デバイス名ごとに、 `ClearTypeLevel` DWORD 値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-139">For each display device name for a user, a `ClearTypeLevel` DWORD value is defined.</span></span> <span data-ttu-id="3f01f-140">次のスクリーンショットは、ClearType レベルのレジストリエディターの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f01f-140">The following screenshot shows the Registry Editor setting for the ClearType level.</span></span>  
  
 ![レジストリエディターの ClearType 設定。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="3f01f-142">アプリケーションは、ClearType の有無にかかわらず、2つのモードのいずれかでテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-142">applications render text in one of either two modes, with and without ClearType.</span></span> <span data-ttu-id="3f01f-143">ClearType を使用せずにテキストを表示する場合は、グレースケールレンダリングと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-143">When text is rendered without ClearType, it is referred to as gray scale rendering.</span></span>  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a><span data-ttu-id="3f01f-144">ガンマ レベル</span><span class="sxs-lookup"><span data-stu-id="3f01f-144">Gamma Level</span></span>  
 <span data-ttu-id="3f01f-145">ガンマ レベルとは、ピクセル値と輝度間の非線形リレーションシップのことです。</span><span class="sxs-lookup"><span data-stu-id="3f01f-145">The gamma level refers to the nonlinear relationship between a pixel value and luminance.</span></span> <span data-ttu-id="3f01f-146">ガンマ レベル設定は、ディスプレイ デバイスの物理特性に対応する必要があります。対応していない場合、レンダリング出力にゆがみが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-146">The gamma level setting should correspond to the physical characteristics of the display device; otherwise, distortions in rendered output may occur.</span></span> <span data-ttu-id="3f01f-147">たとえば、テキストの表示が広すぎたり狭すぎたりする場合や、色縁がグリフの縦線の端に表示される場合などがあります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-147">For example, test may appear too wide or too narrow, or color fringes may appear on the edges of vertical stems of glyphs.</span></span>  
  
 <span data-ttu-id="3f01f-148">ガンマ レベルは、1000 から 2200 の範囲の整数値です。</span><span class="sxs-lookup"><span data-stu-id="3f01f-148">The gamma level is an integer value that ranges from 1000 to 2200.</span></span> <span data-ttu-id="3f01f-149">既定のレベルは 1900 です。</span><span class="sxs-lookup"><span data-stu-id="3f01f-149">The default level is 1900.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="3f01f-150">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="3f01f-150">Registry Setting</span></span>  
 <span data-ttu-id="3f01f-151">ガンマ レベルのレジストリ設定は、特定のディスプレイ デバイス名に対応するローカル マシン設定の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-151">The registry setting location for the gamma level is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="3f01f-152">ユーザーの表示デバイス名ごとに、 `GammaLevel` DWORD 値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-152">For each display device name for a user, a `GammaLevel` DWORD value is defined.</span></span> <span data-ttu-id="3f01f-153">次のスクリーンショットは、ガンマ レベルのレジストリ エディターの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f01f-153">The following screenshot shows the Registry Editor setting for the gamma level.</span></span>  
  
 ![レジストリエディターの ClearType ガンマレベル設定](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a><span data-ttu-id="3f01f-155">ピクセル構造</span><span class="sxs-lookup"><span data-stu-id="3f01f-155">Pixel Structure</span></span>  
 <span data-ttu-id="3f01f-156">ピクセル構造は、ディスプレイ デバイスを構成するピクセルの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-156">The pixel structure describes the type of pixels that make up a display device.</span></span> <span data-ttu-id="3f01f-157">ピクセル構造は、次の 3 種類のいずれかとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-157">The pixel structure is defined as one of three types:</span></span>  
  
|<span data-ttu-id="3f01f-158">種類</span><span class="sxs-lookup"><span data-stu-id="3f01f-158">Type</span></span>|<span data-ttu-id="3f01f-159">Value</span><span class="sxs-lookup"><span data-stu-id="3f01f-159">Value</span></span>|<span data-ttu-id="3f01f-160">説明</span><span class="sxs-lookup"><span data-stu-id="3f01f-160">Description</span></span>|  
|----------|-----------|-----------------|  
|<span data-ttu-id="3f01f-161">フラット</span><span class="sxs-lookup"><span data-stu-id="3f01f-161">Flat</span></span>|<span data-ttu-id="3f01f-162">0</span><span class="sxs-lookup"><span data-stu-id="3f01f-162">0</span></span>|<span data-ttu-id="3f01f-163">ディスプレイ デバイスにピクセル構造がありません。</span><span class="sxs-lookup"><span data-stu-id="3f01f-163">The display device has no pixel structure.</span></span> <span data-ttu-id="3f01f-164">つまり、各色の光源がピクセル領域に均等に拡散しています。これは、グレースケール レンダリングと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-164">This means that light sources for each color are spread equally on the pixel area—this is referred to as gray scale rendering.</span></span> <span data-ttu-id="3f01f-165">標準のディスプレイ デバイスはこのようにして機能します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-165">This is how a standard display device works.</span></span> <span data-ttu-id="3f01f-166">表示されるテキストに ClearType が適用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="3f01f-166">ClearType is never applied to the rendered text.</span></span>|  
|<span data-ttu-id="3f01f-167">RGB</span><span class="sxs-lookup"><span data-stu-id="3f01f-167">RGB</span></span>|<span data-ttu-id="3f01f-168">1</span><span class="sxs-lookup"><span data-stu-id="3f01f-168">1</span></span>|<span data-ttu-id="3f01f-169">ディスプレイ デバイスのピクセルは、赤、緑、青の順の 3 つのストライプで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-169">The display device has pixels that consist of three stripes in the following order: red, green, and blue.</span></span> <span data-ttu-id="3f01f-170">表示されるテキストに ClearType が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-170">ClearType is applied to the rendered text.</span></span>|  
|<span data-ttu-id="3f01f-171">BGR</span><span class="sxs-lookup"><span data-stu-id="3f01f-171">BGR</span></span>|<span data-ttu-id="3f01f-172">2</span><span class="sxs-lookup"><span data-stu-id="3f01f-172">2</span></span>|<span data-ttu-id="3f01f-173">ディスプレイ デバイスのピクセルは、青、緑、赤の順の 3 つのストライプで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-173">The display device has pixels that consist of three stripes in the following order: blue, green, and red.</span></span> <span data-ttu-id="3f01f-174">表示されるテキストに ClearType が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-174">ClearType is applied to the rendered text.</span></span> <span data-ttu-id="3f01f-175">順序が RGB の場合の逆であることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="3f01f-175">Notice how the order is inverted from the RGB type.</span></span>|  
  
 <span data-ttu-id="3f01f-176">ピクセル構造は、0 から 2 の範囲の整数値に対応します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-176">The pixel structure corresponds to an integer value that ranges from 0 to 2.</span></span> <span data-ttu-id="3f01f-177">既定のレベルは 0 です。これは、フラット ピクセル構造を表します。</span><span class="sxs-lookup"><span data-stu-id="3f01f-177">The default level is 0, which represents a flat pixel structure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f01f-178">表示デバイス名の列挙の詳細について`EnumDisplayDevices`は、 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]関数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f01f-178">For information on enumerating display device names, see the `EnumDisplayDevices`[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="3f01f-179">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="3f01f-179">Registry Setting</span></span>  
 <span data-ttu-id="3f01f-180">ピクセル構造のレジストリ設定は、特定のディスプレイ デバイス名に対応するローカル マシン設定の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-180">The registry setting location for the pixel structure is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="3f01f-181">ユーザーの表示デバイス名ごとに、 `PixelStructure` DWORD 値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-181">For each display device name for a user, a `PixelStructure` DWORD value is defined.</span></span> <span data-ttu-id="3f01f-182">次のスクリーンショットは、ピクセル構造のレジストリ エディターの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f01f-182">The following screenshot shows the Registry Editor setting for the pixel structure.</span></span>  
  
 ![レジストリエディターの ClearType ガンマレベル設定](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a><span data-ttu-id="3f01f-184">テキストのコントラスト レベル</span><span class="sxs-lookup"><span data-stu-id="3f01f-184">Text Contrast Level</span></span>  
 <span data-ttu-id="3f01f-185">テキストのコントラスト レベルを設定すると、グリフの縦線の幅に基づいてテキストのレンダリングを調整できます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-185">The text contrast level allows you to adjust the rendering of text based on the stem widths of glyphs.</span></span> <span data-ttu-id="3f01f-186">テキストのコントラスト レベルは 0 から 6 の範囲の整数値です。整数値を大きくすると、縦線の幅が広くなります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-186">The text contrast level is an integer value that ranges from 0 to 6—the larger the integer value, the wider the stem.</span></span> <span data-ttu-id="3f01f-187">既定のレベルは 1 です。</span><span class="sxs-lookup"><span data-stu-id="3f01f-187">The default level is 1.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="3f01f-188">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="3f01f-188">Registry Setting</span></span>  
 <span data-ttu-id="3f01f-189">テキストのコントラスト レベルのレジストリ設定は、特定のディスプレイ デバイス名に対応する個々のユーザー設定の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="3f01f-189">The registry setting location for the text contrast level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="3f01f-190">ユーザーの表示デバイス名ごとに、 `TextContrastLevel` DWORD 値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="3f01f-190">For each display device name for a user, a `TextContrastLevel` DWORD value is defined.</span></span> <span data-ttu-id="3f01f-191">次のスクリーンショットは、テキストのコントラスト レベルのレジストリ エディターの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f01f-191">The following screenshot shows the Registry Editor setting for the text contrast level.</span></span>  
  
 ![レジストリエディターの ClearType 設定。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a><span data-ttu-id="3f01f-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f01f-193">See also</span></span>

- [<span data-ttu-id="3f01f-194">ClearType の概要</span><span class="sxs-lookup"><span data-stu-id="3f01f-194">ClearType Overview</span></span>](cleartype-overview.md)
- [<span data-ttu-id="3f01f-195">ClearType アンチエイリアシング</span><span class="sxs-lookup"><span data-stu-id="3f01f-195">ClearType Antialiasing</span></span>](/windows/desktop/gdi/cleartype-antialiasing)
