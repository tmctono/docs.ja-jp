---
title: 'チュートリアル: Win32 での WPF クロックのホスト'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 98e48060bbb82764e1e541797c666ca33f247c39
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400482"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="f386a-102">チュートリアル: Win32 での WPF クロックのホスト</span><span class="sxs-lookup"><span data-stu-id="f386a-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="f386a-103">アプリケーション内[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]に配置するに<xref:System.Windows.Interop.HwndSource>は、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]を使用します。これにより、コンテンツを含む HWND が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f386a-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="f386a-104">最初にを作成<xref:System.Windows.Interop.HwndSource>し、CreateWindow のようなパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="f386a-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="f386a-105"><xref:System.Windows.Interop.HwndSource> 次[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]に、その中に必要なコンテンツについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f386a-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="f386a-106">最後に、から HWND <xref:System.Windows.Interop.HwndSource>を取得します。</span><span class="sxs-lookup"><span data-stu-id="f386a-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="f386a-107">このチュートリアルでは、[オペレーティングシステム[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]の[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] **日付と時刻のプロパティ**] ダイアログを再実装する、混在するアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f386a-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f386a-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f386a-108">Prerequisites</span></span>

<span data-ttu-id="f386a-109">「 [WPF と Win32 の相互運用」を](wpf-and-win32-interoperation.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="f386a-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="f386a-110">このチュートリアルの使用方法</span><span class="sxs-lookup"><span data-stu-id="f386a-110">How to Use This Tutorial</span></span>

<span data-ttu-id="f386a-111">このチュートリアルでは、相互運用アプリケーションを生成するための重要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f386a-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="f386a-112">このチュートリアルは、サンプルの[Win32 クロック相互運用のサンプル](https://go.microsoft.com/fwlink/?LinkID=160051)によって支えられていますが、そのサンプルは終了製品を反映しています。</span><span class="sxs-lookup"><span data-stu-id="f386a-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="f386a-113">このチュートリアルでは、自分が所有している既存[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]のプロジェクト (おそらく既存のプロジェクト) で作業を開始していて、ホスト[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]されているをアプリケーションに追加している場合と同様の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f386a-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="f386a-114">[Win32 クロック相互運用のサンプル](https://go.microsoft.com/fwlink/?LinkID=160051)を使用して、終了製品を比較することができます。</span><span class="sxs-lookup"><span data-stu-id="f386a-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="f386a-115">Win32 内の Windows Presentation Framework のチュートリアル (System.windows.interop.hwndsource>)</span><span class="sxs-lookup"><span data-stu-id="f386a-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="f386a-116">次の図は、このチュートリアルの目的の最終製品を示しています。</span><span class="sxs-lookup"><span data-stu-id="f386a-116">The following graphic shows the intended end product of this tutorial:</span></span>

![[日付と時刻のプロパティ] ダイアログボックスを表示するスクリーンショット。](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="f386a-118">このダイアログを再作成するにはC++ 、Visual Studio で Win32 プロジェクトを作成し、ダイアログエディターを使用して次のものを作成します。</span><span class="sxs-lookup"><span data-stu-id="f386a-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![[再作成された日付と時刻のプロパティ] ダイアログボックス](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="f386a-120">(を使用するためにを[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]使用する<xref:System.Windows.Interop.HwndSource>必要はありませんが、プログラムC++の作成[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]にを使用する必要はありませんが、これは非常に一般的な方法であり、ステップごとのチュートリアルの説明に適しています)。</span><span class="sxs-lookup"><span data-stu-id="f386a-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="f386a-121">ダイアログに時計を[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]配置するには、5つの特定の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f386a-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="f386a-122">でプロジェクト[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]の設定を変更することにより、プロジェクトで[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]マネージコード ( **/clr**) を呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="f386a-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>

2. <span data-ttu-id="f386a-123">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を<xref:System.Windows.Controls.Page>別の DLL に作成します。</span><span class="sxs-lookup"><span data-stu-id="f386a-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="f386a-124">を内[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>に配置します。 <xref:System.Windows.Interop.HwndSource></span><span class="sxs-lookup"><span data-stu-id="f386a-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="f386a-125">プロパティを使用して<xref:System.Windows.Controls.Page> 、そのの HWND を取得します。 <xref:System.Windows.Interop.HwndSource.Handle%2A></span><span class="sxs-lookup"><span data-stu-id="f386a-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="f386a-126">より[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 大きな[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]アプリケーション内で HWND を配置する場所を決定するために使用します</span><span class="sxs-lookup"><span data-stu-id="f386a-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>

## <a name="clr"></a><span data-ttu-id="f386a-127">/clr</span><span class="sxs-lookup"><span data-stu-id="f386a-127">/clr</span></span>

<span data-ttu-id="f386a-128">最初の手順では、アン[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]マネージプロジェクトをマネージコードを呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="f386a-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span> <span data-ttu-id="f386a-129">/Clr コンパイラオプションを使用します。このオプションは、使用する必要な Dll にリンクし、で[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用するための Main メソッドを調整します。</span><span class="sxs-lookup"><span data-stu-id="f386a-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="f386a-130">C++プロジェクト内でマネージコードを使用できるようにするには、次のようにします。Win32clock プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f386a-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="f386a-131">**全般** プロパティページ (既定) で、共通言語ランタイムサポート `/clr`をに変更します。</span><span class="sxs-lookup"><span data-stu-id="f386a-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="f386a-132">次に、に必要な Dll へ[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]の参照を追加します。プレゼンテーションのコア .dll、プレゼンテーションフレームワーク .dll、.dll、WindowsBase .dll、Uiautomationprovider.dll、および Uiautomationtypes.dll があります。</span><span class="sxs-lookup"><span data-stu-id="f386a-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="f386a-133">(以下の手順は、オペレーティングシステムが C: ドライブにインストールされていることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="f386a-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="f386a-134">Win32clock project を右クリックし、**参照** をクリックして、そのダイアログ内でを選択します。</span><span class="sxs-lookup"><span data-stu-id="f386a-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="f386a-135">Win32clock プロジェクト を右クリックし、**参照** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f386a-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="f386a-136">**新しい参照の追加** をクリックし、参照 タブをクリックして、「C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll」と入力し、OK をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f386a-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="f386a-137">プレゼンテーションフレームワーク .dll に対して繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="f386a-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="f386a-138">WindowsBase .dll に対してこの手順を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="f386a-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="f386a-139">Uiautomationtypes.dll に対してこの手順を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="f386a-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="f386a-140">Uiautomationprovider.dll に対してこの手順を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="f386a-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="f386a-141">**新しい参照の追加** をクリックし、.dll を選択して、 **OK**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f386a-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="f386a-142">**[OK]** をクリックして、参照を追加するための Win32clock プロパティページを終了します。</span><span class="sxs-lookup"><span data-stu-id="f386a-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="f386a-143">最後に、を`STAThreadAttribute`と共`_tWinMain` [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]に使用するために、をメソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="f386a-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="f386a-144">この属性は、初期化[!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]時に共通言語ランタイム (CLR) に通知します。これは、(および[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]) に[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]必要なシングルスレッドアパートメントモデル (STA) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f386a-144">This attribute tells the common language runtime (CLR) that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="f386a-145">Windows Presentation Framework ページを作成する</span><span class="sxs-lookup"><span data-stu-id="f386a-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="f386a-146">次に、を[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>定義する DLL を作成します。</span><span class="sxs-lookup"><span data-stu-id="f386a-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="f386a-147">多くの場合、をスタンドアロン[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション<xref:System.Windows.Controls.Page>として作成[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]し、その部分を記述してデバッグするのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="f386a-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="f386a-148">完了したら、プロジェクトを右クリックし、**プロパティ** をクリックして、アプリケーションに移動し、出力の種類 を Windows クラスライブラリ に変更することにより、そのプロジェクトを DLL に変換できます。</span><span class="sxs-lookup"><span data-stu-id="f386a-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="f386a-149">Dll プロジェクトは、 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]プロジェクト (2 つのプロジェクトを含む1つのソリューション) と組み合わせることができます。ソリューションを右クリックし、 **[Add\Existing プロジェクト]** を選択します。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f386a-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="f386a-150">プロジェクトからその[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll を使用するには、参照を追加する必要があります。 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f386a-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>

1. <span data-ttu-id="f386a-151">Win32clock プロジェクト を右クリックし、**参照** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f386a-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="f386a-152">**[新しい参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f386a-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="f386a-153">**[プロジェクト]** タブをクリックします。WPFClock を選択し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f386a-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="f386a-154">**[OK]** をクリックして、参照を追加するための Win32clock プロパティページを終了します。</span><span class="sxs-lookup"><span data-stu-id="f386a-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="f386a-155">System.windows.interop.hwndsource></span><span class="sxs-lookup"><span data-stu-id="f386a-155">HwndSource</span></span>

<span data-ttu-id="f386a-156">次に、を<xref:System.Windows.Interop.HwndSource>使用して[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 、HWND の<xref:System.Windows.Controls.Page>ように表示します。</span><span class="sxs-lookup"><span data-stu-id="f386a-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="f386a-157">次のコードブロックをC++ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f386a-157">You add this block of code to a C++ file:</span></span>

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

 <span data-ttu-id="f386a-158">これは、何らかの説明を使用できる長いコードです。</span><span class="sxs-lookup"><span data-stu-id="f386a-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="f386a-159">最初の部分はさまざまな句であり、すべての呼び出しを完全に修飾する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="f386a-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="f386a-160">次に、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コンテンツを作成して<xref:System.Windows.Interop.HwndSource>周囲に配置し、HWND を返す関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="f386a-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="f386a-161">まず、パラメーターが<xref:System.Windows.Interop.HwndSource>CreateWindow に似ているを作成します。</span><span class="sxs-lookup"><span data-stu-id="f386a-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

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

<span data-ttu-id="f386a-162">次に、その[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コンストラクターを呼び出してコンテンツクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f386a-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="f386a-163">次に、 <xref:System.Windows.Interop.HwndSource>ページをに接続します。</span><span class="sxs-lookup"><span data-stu-id="f386a-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="f386a-164">最後の行で、の HWND <xref:System.Windows.Interop.HwndSource>を返します。</span><span class="sxs-lookup"><span data-stu-id="f386a-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="f386a-165">Hwnd の配置</span><span class="sxs-lookup"><span data-stu-id="f386a-165">Positioning the Hwnd</span></span>

<span data-ttu-id="f386a-166">これで、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]時計を含む hwnd が作成されたので、この hwnd を[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]ダイアログ内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f386a-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span> <span data-ttu-id="f386a-167">HWND をどこに配置するかがわかっていれば、先ほど定義した`GetHwnd`関数にそのサイズと場所を渡すだけです。</span><span class="sxs-lookup"><span data-stu-id="f386a-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="f386a-168">ただし、リソースファイルを使用してダイアログを定義したので、Hwnd がどこに配置されているかを正確に確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="f386a-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="f386a-169">[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]ダイアログエディターを使用して、時計の[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]移動先 ("ここに時計を挿入する") に静的コントロールを配置し、それを[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用して時計を配置できます。</span><span class="sxs-lookup"><span data-stu-id="f386a-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="f386a-170">WM_INITDIALOG を処理する場合は、 `GetDlgItem`を使用して、プレースホルダー STATIC の HWND を取得します。</span><span class="sxs-lookup"><span data-stu-id="f386a-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="f386a-171">次に、そのプレースホルダーのサイズと位置を計算し、その場所に時計[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]を配置できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f386a-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="f386a-172">RECT 四角形;</span><span class="sxs-lookup"><span data-stu-id="f386a-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="f386a-173">次に、プレースホルダーを静的に非表示にします。</span><span class="sxs-lookup"><span data-stu-id="f386a-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="f386a-174">次のよう[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]に、その場所に時計 HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="f386a-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="f386a-175">このチュートリアルをおもしろいものにし、実際[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]の時計を生成するには、この時点で時計コントロールを[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f386a-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="f386a-176">多くの場合、コードビハインドでいくつかのイベントハンドラーを使用するだけで、マークアップでこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f386a-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="f386a-177">このチュートリアルは相互運用に関するものであり、コントロールの設計に関する[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ものではないため、この時計の完全なコードはコードブロックとして提供されています。これは、ビルドのための個別の指示や各部分の意味を持ちません。</span><span class="sxs-lookup"><span data-stu-id="f386a-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="f386a-178">このコードを自由に試して、コントロールの外観や外観を変更してください。</span><span class="sxs-lookup"><span data-stu-id="f386a-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="f386a-179">マークアップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f386a-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="f386a-180">次に、関連する分離コードを示します。</span><span class="sxs-lookup"><span data-stu-id="f386a-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="f386a-181">最終的な結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f386a-181">The final result looks like:</span></span>

![[最終結果の日付と時刻のプロパティ] ダイアログボックス](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="f386a-183">このスクリーンショットを生成したコードと結果を比較するには、「 [Win32 Clock 相互運用のサンプル](https://go.microsoft.com/fwlink/?LinkID=160051)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f386a-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="f386a-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="f386a-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="f386a-185">WPF と Win32 の相互運用性</span><span class="sxs-lookup"><span data-stu-id="f386a-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="f386a-186">Win32 クロック相互運用のサンプル</span><span class="sxs-lookup"><span data-stu-id="f386a-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
