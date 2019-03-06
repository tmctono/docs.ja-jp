---
title: 'チュートリアル: Win32 での WPF クロックのホスト'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: a13e21281a4bdb365c3a0541d88cd94b6476492e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494949"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="52096-102">チュートリアル: Win32 での WPF クロックのホスト</span><span class="sxs-lookup"><span data-stu-id="52096-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="52096-103">配置する[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]アプリケーションに、<xref:System.Windows.Interop.HwndSource>を含む HWND を提供する、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="52096-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="52096-104">最初に作成、 <xref:System.Windows.Interop.HwndSource>CreateWindow のようなパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="52096-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="52096-105">わかり、<xref:System.Windows.Interop.HwndSource>について、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内するコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="52096-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="52096-106">最後に、out の HWND を取得する、<xref:System.Windows.Interop.HwndSource>します。</span><span class="sxs-lookup"><span data-stu-id="52096-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="52096-107">このチュートリアルは、混合を作成する方法を示しています。[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]オペレーティング システムを reimplements アプリケーション**日付と時刻のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="52096-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52096-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="52096-108">Prerequisites</span></span>

<span data-ttu-id="52096-109">参照してください[WPF と Win32 の相互運用性](wpf-and-win32-interoperation.md)します。</span><span class="sxs-lookup"><span data-stu-id="52096-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="52096-110">このチュートリアルを使用する方法</span><span class="sxs-lookup"><span data-stu-id="52096-110">How to Use This Tutorial</span></span>

<span data-ttu-id="52096-111">このチュートリアルは相互運用アプリケーションの作成の重要な手順に重点を置いて説明します。</span><span class="sxs-lookup"><span data-stu-id="52096-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="52096-112">このチュートリアルはサンプルについては、によって支えられて[Win32 クロックの相互運用性サンプル](https://go.microsoft.com/fwlink/?LinkID=160051)が、そのサンプルは、最終的な製品の反射します。</span><span class="sxs-lookup"><span data-stu-id="52096-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="52096-113">既存の開始された場合、このチュートリアル手順について説明[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]独自のプロジェクトや既存のプロジェクトなどをホストされた追加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションにします。</span><span class="sxs-lookup"><span data-stu-id="52096-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="52096-114">最終的な製品を比較する[Win32 クロックの相互運用性サンプル](https://go.microsoft.com/fwlink/?LinkID=160051)します。</span><span class="sxs-lookup"><span data-stu-id="52096-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="52096-115">Win32 内部の Windows Presentation Framework のチュートリアル (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="52096-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="52096-116">次の図は、このチュートリアルの目的の最終製品を示します。</span><span class="sxs-lookup"><span data-stu-id="52096-116">The following graphic shows the intended end product of this tutorial:</span></span>

<span data-ttu-id="52096-117">![日付と時刻のプロパティ ダイアログ ボックス](./media/interoparch06.PNG "InteropArch06")</span><span class="sxs-lookup"><span data-stu-id="52096-117">![Date and Time Properties dialog box](./media/interoparch06.PNG "InteropArch06")</span></span>

<span data-ttu-id="52096-118">C++ を作成してこのダイアログ ボックスを再作成できます[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]プロジェクト[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]、ダイアログ エディターを使用して、次を作成するとします。</span><span class="sxs-lookup"><span data-stu-id="52096-118">You can recreate this dialog by creating C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and using the dialog editor to create the following:</span></span>

<span data-ttu-id="52096-119">![日付と時刻のプロパティ ダイアログ ボックス](./media/interoparch07.PNG "InteropArch07")</span><span class="sxs-lookup"><span data-stu-id="52096-119">![Date and Time Properties dialog box](./media/interoparch07.PNG "InteropArch07")</span></span>

<span data-ttu-id="52096-120">(を使用する必要はありません[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]を使用する<xref:System.Windows.Interop.HwndSource>、C++ を使用して記述する必要はありません[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]、これを行う非常に典型的な方法であり、プログラムが、このステップ チュートリアルについてにも適しています)。</span><span class="sxs-lookup"><span data-stu-id="52096-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="52096-121">配置するには 5 つの特定のサブ手順を実行する必要がある、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  ダイアログにクロックします。</span><span class="sxs-lookup"><span data-stu-id="52096-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="52096-122">有効にする、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]マネージ コードを呼び出すためのプロジェクト (**/clr**) プロジェクトの設定を変更することで[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="52096-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>

2. <span data-ttu-id="52096-123">作成、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>個別の DLL にします。</span><span class="sxs-lookup"><span data-stu-id="52096-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="52096-124">追加する[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>内で、<xref:System.Windows.Interop.HwndSource>します。</span><span class="sxs-lookup"><span data-stu-id="52096-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="52096-125">そのため、HWND を取得<xref:System.Windows.Controls.Page>を使用して、<xref:System.Windows.Interop.HwndSource.Handle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="52096-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="52096-126">使用[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]内で、大規模な HWND を配置する場所を決定する[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]アプリケーション</span><span class="sxs-lookup"><span data-stu-id="52096-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>

## <a name="clr"></a><span data-ttu-id="52096-127">/clr</span><span class="sxs-lookup"><span data-stu-id="52096-127">/clr</span></span>

<span data-ttu-id="52096-128">この管理対象外にするには、まず[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]プロジェクトを呼び出すことができる 1 つにマネージ コード。</span><span class="sxs-lookup"><span data-stu-id="52096-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span> <span data-ttu-id="52096-129">Main メソッドで使用するために調整し、使用するために必要な Dll へのリンクは、/clr コンパイラ オプションを使用する[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="52096-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="52096-130">C++ プロジェクト内のマネージ コードの使用を有効にします。Win32clock プロジェクトを右クリックし、選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="52096-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="52096-131">**全般**プロパティ ページ (既定)、変更を共通言語ランタイム サポート`/clr`します。</span><span class="sxs-lookup"><span data-stu-id="52096-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="52096-132">次に、必要な Dll への参照を追加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:Presentationcore.dll 内、PresentationFramework.dll、System.dll、WindowsBase.dll、UIAutomationProvider.dll および UIAutomationTypes.dll します。</span><span class="sxs-lookup"><span data-stu-id="52096-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="52096-133">(次の手順と仮定 c: ドライブに、オペレーティング システムがインストールされている。)</span><span class="sxs-lookup"><span data-stu-id="52096-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="52096-134">Win32clock プロジェクトを右クリックして**参照.**、およびそのダイアログ内。</span><span class="sxs-lookup"><span data-stu-id="52096-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="52096-135">Win32clock プロジェクトを右クリックして**参照.**.</span><span class="sxs-lookup"><span data-stu-id="52096-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="52096-136">クリックして**新しい参照の追加**[参照] タブをクリックして、C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll を入力して [ok] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52096-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="52096-137">PresentationFramework.dll を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll します。</span><span class="sxs-lookup"><span data-stu-id="52096-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="52096-138">WindowsBase.dll を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll します。</span><span class="sxs-lookup"><span data-stu-id="52096-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="52096-139">UIAutomationTypes.dll を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="52096-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="52096-140">UIAutomationProvider.dll を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="52096-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="52096-141">をクリックして**新しい参照の追加**、System.dll を選択して、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="52096-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="52096-142">クリックして**OK**参照の追加の win32clock プロパティ ページを終了します。</span><span class="sxs-lookup"><span data-stu-id="52096-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="52096-143">最後に、追加、`STAThreadAttribute`を`_tWinMain`メソッドで使用するため[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="52096-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="52096-144">この属性は、[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]を初期化した[!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]、必要なシングル スレッド アパートメント モデル (STA) を使用する必要があります[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (と[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="52096-144">This attribute tells the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="52096-145">Windows Presentation Framework ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="52096-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="52096-146">次に、定義する DLL を作成、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>します。</span><span class="sxs-lookup"><span data-stu-id="52096-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="52096-147">作成する最も簡単なことがよくあります、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>としてスタンドアロン アプリケーション、および書き込みとデバッグ、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]部分のことです。</span><span class="sxs-lookup"><span data-stu-id="52096-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="52096-148">クリックすると、プロジェクトを右クリックし、DLL にそのプロジェクトを変換できますが終わったら、**プロパティ**しようとして、アプリケーションや Windows クラス ライブラリに出力の種類を変更します。</span><span class="sxs-lookup"><span data-stu-id="52096-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="52096-149">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Dll プロジェクトを結合できます、 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 、ソリューションを右クリックしてプロジェクト (1 つのソリューションを 2 つのプロジェクトを含む) – **Add\Existing プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="52096-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="52096-150">それを使用する[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]から dll、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]プロジェクトの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52096-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>

1. <span data-ttu-id="52096-151">Win32clock プロジェクトを右クリックして**参照.**.</span><span class="sxs-lookup"><span data-stu-id="52096-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="52096-152">クリックして**新しい参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="52096-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="52096-153">**[プロジェクト]** タブをクリックします。WPFClock を選択して、[ok] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52096-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="52096-154">クリックして**OK**参照の追加の win32clock プロパティ ページを終了します。</span><span class="sxs-lookup"><span data-stu-id="52096-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="52096-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="52096-155">HwndSource</span></span>

<span data-ttu-id="52096-156">次に、<xref:System.Windows.Interop.HwndSource>させる、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> HWND のようになります。</span><span class="sxs-lookup"><span data-stu-id="52096-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="52096-157">C++ ファイルには、このコード ブロックを追加します。</span><span class="sxs-lookup"><span data-stu-id="52096-157">You add this block of code to a C++ file:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;

    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
        HwndSource^ source = gcnew HwndSource(
            0, // class style
            WS_VISIBLE | WS_CHILD, // style
            0, // exstyle
            x, y, width, height,
            "hi", // NAME
            IntPtr(parent)        // parent window
            );

        UIElement^ page = gcnew WPFClock::Clock();
        source->RootVisual = page;
        return (HWND) source->Handle.ToPointer();
    }
}
}
```

 <span data-ttu-id="52096-158">これは、長いが、いくつか説明を使用できるコードです。</span><span class="sxs-lookup"><span data-stu-id="52096-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="52096-159">最初の部分では、すべての呼び出しを完全に修飾する必要はありませんように各種の句は。</span><span class="sxs-lookup"><span data-stu-id="52096-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="52096-160">作成する関数を定義し、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コンテンツ、put、<xref:System.Windows.Interop.HwndSource>および HWND を返します。</span><span class="sxs-lookup"><span data-stu-id="52096-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="52096-161">最初に作成、<xref:System.Windows.Interop.HwndSource>パラメーターを持つ、CreateWindow に似ています。</span><span class="sxs-lookup"><span data-stu-id="52096-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

<span data-ttu-id="52096-162">作成し、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コンテンツ クラスのコンス トラクターを呼び出して。</span><span class="sxs-lookup"><span data-stu-id="52096-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="52096-163">ページに接続して、 <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="52096-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="52096-164">最後の行での HWND を返すと、 <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="52096-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="52096-165">Hwnd を配置</span><span class="sxs-lookup"><span data-stu-id="52096-165">Positioning the Hwnd</span></span>

<span data-ttu-id="52096-166">含む HWND をしたら、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]時計の内部には、その HWND を配置する必要があります、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="52096-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span> <span data-ttu-id="52096-167">そのサイズと場所を渡す場合だけ、HWND を配置する場所がわかっている場合、`GetHwnd`前に定義する関数。</span><span class="sxs-lookup"><span data-stu-id="52096-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="52096-168">Hwnd のいずれかが配置されていることはよくわかっていません、ダイアログ ボックスを定義するリソース ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="52096-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="52096-169">使用することができます、[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]にダイアログ エディター、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]スタティック コントロール、クロックを移動する (「Insert 制ここで」)、配置する際に使用、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]クロック。</span><span class="sxs-lookup"><span data-stu-id="52096-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="52096-170">WM_INITDIALOG を処理する場所を使用する`GetDlgItem`静的なプレース ホルダーの HWND を取得します。</span><span class="sxs-lookup"><span data-stu-id="52096-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="52096-171">計算する静的なプレース ホルダーの位置とサイズ配置できるように、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]その場所にクロックします。</span><span class="sxs-lookup"><span data-stu-id="52096-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="52096-172">RECT 四角形。</span><span class="sxs-lookup"><span data-stu-id="52096-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="52096-173">静的なプレース ホルダーが非表示します。</span><span class="sxs-lookup"><span data-stu-id="52096-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="52096-174">作成し、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND をその場所でのクロックします。</span><span class="sxs-lookup"><span data-stu-id="52096-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="52096-175">チュートリアルの興味深いにして、実数を生成するために[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]クロックを作成する必要が、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コントロールをこの時点でクロックします。</span><span class="sxs-lookup"><span data-stu-id="52096-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="52096-176">分離コードで、いくつかのイベント ハンドラーを持つため、マークアップで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="52096-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="52096-177">以降、このチュートリアルは、相互運用の概要と、コントロールのデザインはありませんが、完了のコード、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]クロックが提供されるここでは不連続の手順ビルドまたは各部分が何を意味せず、コードのブロックとして。</span><span class="sxs-lookup"><span data-stu-id="52096-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="52096-178">自由に外観やコントロールの機能を変更するには、このコードを実験できます。</span><span class="sxs-lookup"><span data-stu-id="52096-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="52096-179">マークアップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="52096-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="52096-180">付随する分離コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="52096-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="52096-181">最終的な結果は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="52096-181">The final result looks like:</span></span>

<span data-ttu-id="52096-182">![日付と時刻のプロパティ ダイアログ ボックス](./media/interoparch08.PNG "InteropArch08")</span><span class="sxs-lookup"><span data-stu-id="52096-182">![Date and Time Properties dialog box](./media/interoparch08.PNG "InteropArch08")</span></span>

<span data-ttu-id="52096-183">このスクリーン ショットを生成するコードに、最終結果を比較するを参照してください。 [Win32 クロックの相互運用性サンプル](https://go.microsoft.com/fwlink/?LinkID=160051)します。</span><span class="sxs-lookup"><span data-stu-id="52096-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="52096-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="52096-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="52096-185">WPF と Win32 の相互運用性</span><span class="sxs-lookup"><span data-stu-id="52096-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="52096-186">Win32 相互運用のクロックのサンプル</span><span class="sxs-lookup"><span data-stu-id="52096-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
