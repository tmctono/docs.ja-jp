---
title: 'チュートリアル: Win32 で WPF の時計をホストする'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 0aecde96d182e12ab72b1a6cba129ab1d8a28391
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123780"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a><span data-ttu-id="572d6-102">チュートリアル: Win32 で WPF の時計をホストする</span><span class="sxs-lookup"><span data-stu-id="572d6-102">Walkthrough: Host a WPF Clock in Win32</span></span>

<span data-ttu-id="572d6-103">Win32 アプリケーション内に [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を配置するには、<xref:System.Windows.Interop.HwndSource> を使用します。これで、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コンテンツを含む HWND を用意できます。</span><span class="sxs-lookup"><span data-stu-id="572d6-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="572d6-104">まず <xref:System.Windows.Interop.HwndSource> を作成し、CreateWindow のようなパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="572d6-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="572d6-105">次に、その中で必要な [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コンテンツについて <xref:System.Windows.Interop.HwndSource> に伝えます。</span><span class="sxs-lookup"><span data-stu-id="572d6-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="572d6-106">最後に、<xref:System.Windows.Interop.HwndSource> から HWND を取得します。</span><span class="sxs-lookup"><span data-stu-id="572d6-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="572d6-107">このチュートリアルでは、Win32 アプリケーション内に、オペレーティング システムの **[日付と時刻のプロパティ]** ダイアログを実装し直した混合 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="572d6-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="572d6-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="572d6-108">Prerequisites</span></span>

<span data-ttu-id="572d6-109">「[WPF と Win32 の相互運用性](wpf-and-win32-interoperation.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="572d6-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="572d6-110">このチュートリアルの使用方法</span><span class="sxs-lookup"><span data-stu-id="572d6-110">How to Use This Tutorial</span></span>

<span data-ttu-id="572d6-111">このチュートリアルでは、相互運用アプリケーションを作成するための重要な手順に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="572d6-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="572d6-112">このチュートリアルはサンプル [Win32 の時計の相互運用性サンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)を利用していますが、このサンプルは完成品のお手本です。</span><span class="sxs-lookup"><span data-stu-id="572d6-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock), but that sample is reflective of the end product.</span></span> <span data-ttu-id="572d6-113">このチュートリアルでは、(実際はお持ちでないかもしれませんが) お持ちの既存の Win32 プロジェクトから始めて、ホストされている [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] をアプリケーションに追加する場合を仮定して手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="572d6-113">This tutorial documents the steps as if you were starting with an existing Win32 project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="572d6-114">完成品は [Win32 の時計の相互運用性サンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)と比較することができます。</span><span class="sxs-lookup"><span data-stu-id="572d6-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="572d6-115">Win32 (HwndSource) 内の Windows Presentation Framework のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="572d6-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="572d6-116">次の図は、このチュートリアルの完成品を示しています。</span><span class="sxs-lookup"><span data-stu-id="572d6-116">The following graphic shows the intended end product of this tutorial:</span></span>

![[日付と時刻のプロパティ] ダイアログ ボックスが表示されたスクリーンショット。](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="572d6-118">このダイアログを再現するには、Visual Studio で C++ Win32 プロジェクトを作成し、ダイアログ エディターを使用して次のものを作成します。</span><span class="sxs-lookup"><span data-stu-id="572d6-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![再現した [日付と時刻のプロパティ] ダイアログ ボックス](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="572d6-120">(<xref:System.Windows.Interop.HwndSource> を使用するために Visual Studio を使用する必要はありません。また、Win32 プログラムを作成するために C++ を使用する必要もありませんが、これはかなり一般的な方法であり、段階的なチュートリアルの説明に適しています)。</span><span class="sxs-lookup"><span data-stu-id="572d6-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write Win32 programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="572d6-121">ダイアログに [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の時計を配置するには、5 つの特定のサブ手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572d6-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="572d6-122">Visual Studio でプロジェクト設定を変更して、Win32 プロジェクトからマネージド コード ( **/clr**) を呼び出せるようにします。</span><span class="sxs-lookup"><span data-stu-id="572d6-122">Enable your Win32 project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="572d6-123">別の DLL に [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> を作成します。</span><span class="sxs-lookup"><span data-stu-id="572d6-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="572d6-124">その [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> を <xref:System.Windows.Interop.HwndSource> 内に配置します。</span><span class="sxs-lookup"><span data-stu-id="572d6-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="572d6-125"><xref:System.Windows.Interop.HwndSource.Handle%2A> プロパティを使用して、その <xref:System.Windows.Controls.Page> の HWND を取得します。</span><span class="sxs-lookup"><span data-stu-id="572d6-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="572d6-126">Win32 を使用して、HWND をより大きな Win32 アプリケーション内のどこに配置するかを決定します</span><span class="sxs-lookup"><span data-stu-id="572d6-126">Use Win32 to decide where to place the HWND within the larger Win32 application</span></span>

## <a name="clr"></a><span data-ttu-id="572d6-127">/clr</span><span class="sxs-lookup"><span data-stu-id="572d6-127">/clr</span></span>

<span data-ttu-id="572d6-128">最初の手順は、このアンマネージ Win32 プロジェクトを、マネージド コードを呼び出すことができるプロジェクトに変えることです。</span><span class="sxs-lookup"><span data-stu-id="572d6-128">The first step is to turn this unmanaged Win32 project into one that can call managed code.</span></span> <span data-ttu-id="572d6-129">/clr コンパイラ オプションを使用します。これで、使用する必要な DLL にリンクされされます。また、Main メソッドを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] で使用できるように調整します。</span><span class="sxs-lookup"><span data-stu-id="572d6-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="572d6-130">C++ プロジェクト内でマネージド コードの使用を有効にするには:win32clock プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572d6-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="572d6-131">**[全般]** プロパティ ページ (既定値) で、共通言語ランタイムのサポートを `/clr` に変更します。</span><span class="sxs-lookup"><span data-stu-id="572d6-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="572d6-132">次に、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] に必要な次の DLL への参照を追加します。PresentationCore.dll、PresentationFramework.dll、System.dll、WindowsBase.dll、UIAutomationProvider.dll、UIAutomationTypes.dll</span><span class="sxs-lookup"><span data-stu-id="572d6-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="572d6-133">(以下の手順では、オペレーティング システムが C: ドライブにインストールされていることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="572d6-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="572d6-134">win32clock プロジェクトを右クリックし、 **[参照]** を選択し、ダイアログ内で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="572d6-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="572d6-135">win32clock プロジェクトを右クリックし、 **[参照]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572d6-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="572d6-136">**[新しい参照の追加]** をクリックし、[参照] タブをクリックし、「C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll」と入力して [OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572d6-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="572d6-137">次の PresentationFramework.dll に対してこの手順を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll。</span><span class="sxs-lookup"><span data-stu-id="572d6-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="572d6-138">次の WindowsBase.dll に対してこの手順を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll。</span><span class="sxs-lookup"><span data-stu-id="572d6-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="572d6-139">次の UIAutomationTypes.dll に対してこの手順を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll。</span><span class="sxs-lookup"><span data-stu-id="572d6-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="572d6-140">次の UIAutomationProvider.dll に対してこの手順を繰り返します。C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll。</span><span class="sxs-lookup"><span data-stu-id="572d6-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="572d6-141">**[新しい参照の追加]** をクリックし、System.dll を選択して **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572d6-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="572d6-142">**[OK]** をクリックして、参照を追加するために win32clock の [プロパティ] ページを終了します。</span><span class="sxs-lookup"><span data-stu-id="572d6-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="572d6-143">最後に、`STAThreadAttribute` を `_tWinMain` メソッドに追加して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="572d6-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="572d6-144">この属性を使用すると、コンポーネント オブジェクト モデル (COM) を初期化するときに、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (および Windows フォーム) に必要なシングル スレッド アパートメント モデル (STA) を使用するように共通言語ランタイム (CLR) に指示することができます。</span><span class="sxs-lookup"><span data-stu-id="572d6-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and Windows Forms).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="572d6-145">Windows Presentation Framework ページを作成する</span><span class="sxs-lookup"><span data-stu-id="572d6-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="572d6-146">次に、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> を定義する DLL を作成します。</span><span class="sxs-lookup"><span data-stu-id="572d6-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="572d6-147">多くの場合、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> をスタンドアロン アプリケーションとして作成し、それに従って [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 部分を記述してデバッグする方法が最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="572d6-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="572d6-148">完了したら、プロジェクトを右クリックし、 **[プロパティ]** をクリックして、アプリケーションに移動し、出力の種類を Windows クラス ライブラリに変更することで、そのプロジェクトを DLL に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="572d6-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="572d6-149">これで [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll プロジェクトを Win32 プロジェクト (2 つのプロジェクトを含む 1 つのソリューション) と組み合わせることができます。ソリューションを右クリックし、 **[既存プロジェクトの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572d6-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the Win32 project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="572d6-150">Win32 プロジェクトから [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll を使用するには、参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572d6-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the Win32 project, you need to add a reference:</span></span>

1. <span data-ttu-id="572d6-151">win32clock プロジェクトを右クリックし、 **[参照]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572d6-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="572d6-152">**[新しい参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572d6-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="572d6-153">**[プロジェクト]** タブをクリックします。WPFClock を選択し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572d6-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="572d6-154">**[OK]** をクリックして、参照を追加するために win32clock の [プロパティ] ページを終了します。</span><span class="sxs-lookup"><span data-stu-id="572d6-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="572d6-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="572d6-155">HwndSource</span></span>

<span data-ttu-id="572d6-156">次に、<xref:System.Windows.Interop.HwndSource> を使用して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> を HWND のようにします。</span><span class="sxs-lookup"><span data-stu-id="572d6-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="572d6-157">次のコード ブロックを C++ ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="572d6-157">You add this block of code to a C++ file:</span></span>

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

 <span data-ttu-id="572d6-158">これは長いコードなので、いくつか説明を加えます。</span><span class="sxs-lookup"><span data-stu-id="572d6-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="572d6-159">すべての呼び出しを完全に修飾する必要がないように、最初の部分にはさまざまな句があります。</span><span class="sxs-lookup"><span data-stu-id="572d6-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="572d6-160">次に、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] のコンテンツを作成し、それを <xref:System.Windows.Interop.HwndSource> で囲み、HWND を返す関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="572d6-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="572d6-161">まず、CreateWindow と同様のパラメーターを持つ <xref:System.Windows.Interop.HwndSource> を作成します。</span><span class="sxs-lookup"><span data-stu-id="572d6-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

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

<span data-ttu-id="572d6-162">次に、コンストラクターを呼び出して [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コンテンツ クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="572d6-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="572d6-163">次に、ページを <xref:System.Windows.Interop.HwndSource> に接続します。</span><span class="sxs-lookup"><span data-stu-id="572d6-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="572d6-164">最後の行で、<xref:System.Windows.Interop.HwndSource> の HWND を返します。</span><span class="sxs-lookup"><span data-stu-id="572d6-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="572d6-165">Hwnd の配置</span><span class="sxs-lookup"><span data-stu-id="572d6-165">Positioning the Hwnd</span></span>

<span data-ttu-id="572d6-166">これで、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の時計を含む HWND が完成したので、その HWND を Win32 ダイアログ内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572d6-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the Win32 dialog.</span></span> <span data-ttu-id="572d6-167">HWND を配置する場所がわかっている場合は、先ほど定義した `GetHwnd` 関数にそのサイズと場所を渡します。</span><span class="sxs-lookup"><span data-stu-id="572d6-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="572d6-168">ただし、リソース ファイルを使用してダイアログを定義しているため、HWND のどこに配置されているかは正確にはわかりません。</span><span class="sxs-lookup"><span data-stu-id="572d6-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="572d6-169">Visual Studio のダイアログ エディターを使用して、Win32 STATIC コントロールを時計の移動先 ("Insert clock here" (ここに時計を挿入)) に配置し、それを使用して [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の時計を配置できます。</span><span class="sxs-lookup"><span data-stu-id="572d6-169">You can use the Visual Studio dialog editor to put a Win32 STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="572d6-170">WM_INITDIALOG を処理する場合、`GetDlgItem` を使用してプレースホルダー STATIC の HWND を取得します。</span><span class="sxs-lookup"><span data-stu-id="572d6-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="572d6-171">次に、そのプレースホルダー STATIC のサイズと位置を計算し、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の時計をその場所に配置できるようにします。</span><span class="sxs-lookup"><span data-stu-id="572d6-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="572d6-172">RECT 四角形;</span><span class="sxs-lookup"><span data-stu-id="572d6-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="572d6-173">次に、プレースホルダー STATIC を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="572d6-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="572d6-174">そして、その場所に [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の時計の HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="572d6-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="572d6-175">このチュートリアルをおもしろくするために、また実際の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の時計を再現するために、この時点で [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の時計コントロールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572d6-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="572d6-176">主にマークアップで、コードビハインドにいくつかのイベント ハンドラーを使用するだけで、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="572d6-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="572d6-177">このチュートリアルは相互運用に関するものであり、コントロールの設計に関するものではないため、ここでは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の時計の完成したコードをコード ブロックとして提供しています。ビルドに関する個別の指示や各部分の意味については説明しません。</span><span class="sxs-lookup"><span data-stu-id="572d6-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="572d6-178">このコードを自由に試して、コントロールの外観や機能を変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="572d6-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="572d6-179">マークアップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="572d6-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="572d6-180">そして、関連するコードビハインドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="572d6-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="572d6-181">最終的な結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="572d6-181">The final result looks like:</span></span>

![最終的な結果の [日付と時刻のプロパティ] ダイアログ ボックス](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="572d6-183">最終的な結果をこのスクリーンショットの生成に使ったコードと比較するには、[Win32 の時計の相互運用性サンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="572d6-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock).</span></span>

## <a name="see-also"></a><span data-ttu-id="572d6-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="572d6-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="572d6-185">WPF と Win32 の相互運用性</span><span class="sxs-lookup"><span data-stu-id="572d6-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="572d6-186">Win32 クロック相互運用のサンプル</span><span class="sxs-lookup"><span data-stu-id="572d6-186">Win32 Clock Interoperation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)
