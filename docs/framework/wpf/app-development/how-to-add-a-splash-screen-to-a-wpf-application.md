---
title: スプラッシュスクリーンを追加する方法
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 39f53e21c40f036c65894b4f275cd5fb414999be
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740450"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="cdbea-102">方法 : スプラッシュ スクリーンを WPF アプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="cdbea-102">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="cdbea-103">このトピックでは、Windows Presentation Foundation (WPF) アプリケーションにスタートアップウィンドウまたは*スプラッシュスクリーン*を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cdbea-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="cdbea-104">既存のイメージをスプラッシュスクリーンとして追加するには</span><span class="sxs-lookup"><span data-stu-id="cdbea-104">To add an existing image as a splash screen</span></span>

1. <span data-ttu-id="cdbea-105">スプラッシュスクリーンに使用するイメージを作成または検索します。</span><span class="sxs-lookup"><span data-stu-id="cdbea-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="cdbea-106">Windows Imaging Component (WIC) でサポートされている任意のイメージ形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdbea-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="cdbea-107">たとえば、BMP、GIF、JPEG、PNG、または TIFF 形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdbea-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2. <span data-ttu-id="cdbea-108">WPF アプリケーションプロジェクトにイメージファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="cdbea-108">Add the image file to the WPF Application project.</span></span>

3. <span data-ttu-id="cdbea-109">**ソリューションエクスプローラー**で、画像を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdbea-109">In **Solution Explorer**, select the image.</span></span>

4. <span data-ttu-id="cdbea-110">プロパティウィンドウで、 **[ビルドアクション]** プロパティのドロップダウン矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cdbea-110">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5. <span data-ttu-id="cdbea-111">ドロップダウンリストから **[SplashScreen]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdbea-111">Select **SplashScreen** from the drop-down list.</span></span>

6. <span data-ttu-id="cdbea-112">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="cdbea-112">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="cdbea-113">スプラッシュスクリーンのイメージが画面の中央に表示され、メインアプリケーションウィンドウが表示されるとフェードします。</span><span class="sxs-lookup"><span data-stu-id="cdbea-113">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="cdbea-114">ビルドからスプラッシュスクリーンを除外するには</span><span class="sxs-lookup"><span data-stu-id="cdbea-114">To exclude the splash screen from build</span></span>

1. <span data-ttu-id="cdbea-115">**ソリューションエクスプローラー**で、スプラッシュスクリーンのイメージを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdbea-115">In **Solution Explorer**, select the splash screen image.</span></span>

2. <span data-ttu-id="cdbea-116">**[プロパティ]** ウィンドウで、[**ビルド] アクション**を **[なし**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="cdbea-116">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="cdbea-117">アプリケーションからスプラッシュスクリーンを削除するには</span><span class="sxs-lookup"><span data-stu-id="cdbea-117">To remove the splash screen from an application</span></span>

<span data-ttu-id="cdbea-118">**ソリューションエクスプローラー**で、スプラッシュスクリーンのイメージを削除します。</span><span class="sxs-lookup"><span data-stu-id="cdbea-118">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdbea-119">参照</span><span class="sxs-lookup"><span data-stu-id="cdbea-119">See also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="cdbea-120">[方法: プロジェクトに既存の項目を追加する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cdbea-120">[How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
