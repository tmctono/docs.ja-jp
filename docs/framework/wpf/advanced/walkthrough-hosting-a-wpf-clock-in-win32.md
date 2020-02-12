---
title: 'チュートリアル: Win32 での WPF クロックのホスト'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 0aecde96d182e12ab72b1a6cba129ab1d8a28391
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123780"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a><span data-ttu-id="ae1b8-102">チュートリアル: Win32 での WPF クロックのホスト</span><span class="sxs-lookup"><span data-stu-id="ae1b8-102">Walkthrough: Host a WPF Clock in Win32</span></span>

<span data-ttu-id="ae1b8-103">Win32 アプリケーション内に [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を配置するには、<xref:System.Windows.Interop.HwndSource>を使用します。これにより、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コンテンツを含む HWND が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="ae1b8-104">まず、<xref:System.Windows.Interop.HwndSource>を作成し、CreateWindow のようなパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="ae1b8-105">次に、その内部に必要な [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コンテンツについて <xref:System.Windows.Interop.HwndSource> を伝えます。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="ae1b8-106">最後に、<xref:System.Windows.Interop.HwndSource>から HWND を取得します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="ae1b8-107">このチュートリアルでは、[オペレーティングシステムの**日付と時刻のプロパティ**] ダイアログを再実装する Win32 アプリケーション内で混合 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae1b8-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="ae1b8-108">Prerequisites</span></span>

<span data-ttu-id="ae1b8-109">「 [WPF と Win32 の相互運用」を](wpf-and-win32-interoperation.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="ae1b8-110">このチュートリアルの使用方法</span><span class="sxs-lookup"><span data-stu-id="ae1b8-110">How to Use This Tutorial</span></span>

<span data-ttu-id="ae1b8-111">このチュートリアルでは、相互運用アプリケーションを生成するための重要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="ae1b8-112">このチュートリアルは、サンプルの[Win32 クロック相互運用のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)によって支えられていますが、そのサンプルは終了製品を反映しています。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock), but that sample is reflective of the end product.</span></span> <span data-ttu-id="ae1b8-113">このチュートリアルでは、独自の既存の Win32 プロジェクト (通常は既存のプロジェクト) を使用して作業を開始し、ホストされている [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] をアプリケーションに追加している場合と同様の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-113">This tutorial documents the steps as if you were starting with an existing Win32 project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="ae1b8-114">[Win32 クロック相互運用のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)を使用して、終了製品を比較することができます。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="ae1b8-115">Win32 内の Windows Presentation Framework のチュートリアル (System.windows.interop.hwndsource>)</span><span class="sxs-lookup"><span data-stu-id="ae1b8-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="ae1b8-116">次の図は、このチュートリアルの目的の最終製品を示しています。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-116">The following graphic shows the intended end product of this tutorial:</span></span>

![[日付と時刻のプロパティ] ダイアログボックスを表示するスクリーンショット。](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="ae1b8-118">このダイアログを再作成するにはC++ 、Visual Studio で Win32 プロジェクトを作成し、ダイアログエディターを使用して次のものを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![[再作成された日付と時刻のプロパティ] ダイアログボックス](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="ae1b8-120">(<xref:System.Windows.Interop.HwndSource>を使用するために Visual Studio を使用する必要はなく、Win32 プログラムを記述C++するためにを使用する必要はありませんが、これは非常に一般的な方法であり、これについてはチュートリアルの説明にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write Win32 programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="ae1b8-121">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の時計をダイアログに入れるには、5つの特定の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="ae1b8-122">Visual Studio でプロジェクト設定を変更することにより、Win32 プロジェクトでマネージコード ( **/clr**) を呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-122">Enable your Win32 project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="ae1b8-123">別の DLL に [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> を作成します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="ae1b8-124">この [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> <xref:System.Windows.Interop.HwndSource>内に配置します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="ae1b8-125"><xref:System.Windows.Interop.HwndSource.Handle%2A> プロパティを使用して、その <xref:System.Windows.Controls.Page> の HWND を取得します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="ae1b8-126">Win32 を使用して、より大きな Win32 アプリケーション内で HWND を配置する場所を決定する</span><span class="sxs-lookup"><span data-stu-id="ae1b8-126">Use Win32 to decide where to place the HWND within the larger Win32 application</span></span>

## <a name="clr"></a><span data-ttu-id="ae1b8-127">/clr</span><span class="sxs-lookup"><span data-stu-id="ae1b8-127">/clr</span></span>

<span data-ttu-id="ae1b8-128">最初の手順では、アンマネージ Win32 プロジェクトをマネージコードを呼び出すことができるものに変換します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-128">The first step is to turn this unmanaged Win32 project into one that can call managed code.</span></span> <span data-ttu-id="ae1b8-129">使用する必要な Dll にリンクする/clr コンパイラオプションを使用して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]で使用するための Main メソッドを調整します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="ae1b8-130">C++プロジェクト内でマネージコードを使用できるようにするには、win32clock プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="ae1b8-131">**全般** プロパティページ (既定) で、共通言語ランタイムサポート を `/clr`に変更します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="ae1b8-132">次に、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]に必要な Dll への参照を追加します。これには、プレゼンテーションの Uiautomationprovider.dll、Uiautomationtypes.dll、WindowsBase .dll、dll、およびを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="ae1b8-133">(以下の手順は、オペレーティングシステムが C: ドライブにインストールされていることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="ae1b8-134">Win32clock project を右クリックし、**参照** をクリックして、そのダイアログ内でを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="ae1b8-135">Win32clock プロジェクト を右クリックし、**参照** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="ae1b8-136">**新しい参照の追加** をクリックし、参照 タブをクリックして、「C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll」と入力し、OK をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="ae1b8-137">プレゼンテーションフレームワーク .dll に対して繰り返します。 C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="ae1b8-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="ae1b8-138">WindowsBase .dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll. に対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="ae1b8-139">Uiautomationtypes.dll の繰り返し: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="ae1b8-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="ae1b8-140">Uiautomationprovider.dll の繰り返し: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="ae1b8-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="ae1b8-141">**新しい参照の追加** をクリックし、.dll を選択して、 **OK**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="ae1b8-142">**[OK]** をクリックして、参照を追加するための Win32clock プロパティページを終了します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="ae1b8-143">最後に、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]で使用するために `STAThreadAttribute` を `_tWinMain` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="ae1b8-144">この属性は、コンポーネントオブジェクトモデル (COM) を初期化するときに、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (および Windows フォーム) に必要なシングルスレッドアパートメントモデル (STA) を使用する必要があることを、共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and Windows Forms).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="ae1b8-145">Windows Presentation Framework ページを作成する</span><span class="sxs-lookup"><span data-stu-id="ae1b8-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="ae1b8-146">次に、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>を定義する DLL を作成します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="ae1b8-147">多くの場合、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> をスタンドアロンアプリケーションとして作成し、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の部分を記述してデバッグする方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="ae1b8-148">完了したら、プロジェクトを右クリックし、**プロパティ** をクリックして、アプリケーションに移動し、出力の種類 を Windows クラスライブラリ に変更することにより、そのプロジェクトを DLL に変換できます。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="ae1b8-149">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll プロジェクトは、Win32 プロジェクト (2 つのプロジェクトを含む1つのソリューション) と組み合わせることができます。ソリューションを右クリックし、 **[Add\Existing プロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the Win32 project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="ae1b8-150">Win32 プロジェクトからこの [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll を使用するには、参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the Win32 project, you need to add a reference:</span></span>

1. <span data-ttu-id="ae1b8-151">Win32clock プロジェクト を右クリックし、**参照** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="ae1b8-152">**[新しい参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="ae1b8-153">**プロジェクト** タブをクリックします。 WPFClock を選択し、OK をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="ae1b8-154">**[OK]** をクリックして、参照を追加するための Win32clock プロパティページを終了します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="ae1b8-155">System.windows.interop.hwndsource></span><span class="sxs-lookup"><span data-stu-id="ae1b8-155">HwndSource</span></span>

<span data-ttu-id="ae1b8-156">次に、<xref:System.Windows.Interop.HwndSource> を使用して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> HWND のように表示します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="ae1b8-157">次のコードブロックをC++ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-157">You add this block of code to a C++ file:</span></span>

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

 <span data-ttu-id="ae1b8-158">これは、何らかの説明を使用できる長いコードです。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="ae1b8-159">最初の部分はさまざまな句であり、すべての呼び出しを完全に修飾する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="ae1b8-160">次に、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コンテンツを作成し、その周囲に <xref:System.Windows.Interop.HwndSource> を配置し、HWND を返す関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="ae1b8-161">まず、CreateWindow と同様のパラメーターを持つ <xref:System.Windows.Interop.HwndSource>を作成します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

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

<span data-ttu-id="ae1b8-162">次に、コンストラクターを呼び出して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="ae1b8-163">次に、ページを <xref:System.Windows.Interop.HwndSource>に接続します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="ae1b8-164">最後の行で、<xref:System.Windows.Interop.HwndSource>の HWND を返します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="ae1b8-165">Hwnd の配置</span><span class="sxs-lookup"><span data-stu-id="ae1b8-165">Positioning the Hwnd</span></span>

<span data-ttu-id="ae1b8-166">これで [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] クロックを含む HWND が作成されたので、この HWND を Win32 ダイアログ内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the Win32 dialog.</span></span> <span data-ttu-id="ae1b8-167">HWND をどこに配置するかがわかっている場合は、先ほど定義した `GetHwnd` 関数にそのサイズと場所を渡します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="ae1b8-168">ただし、リソースファイルを使用してダイアログを定義したので、Hwnd がどこに配置されているかを正確に確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="ae1b8-169">Visual Studio のダイアログエディターを使用して、時計の移動先 ("ここに時計を挿入する") に Win32 スタティックコントロールを配置し、それを使用して [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] クロックを配置することができます。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-169">You can use the Visual Studio dialog editor to put a Win32 STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="ae1b8-170">WM_INITDIALOG を処理する場合は、`GetDlgItem` を使用して、プレースホルダー STATIC の HWND を取得します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="ae1b8-171">次に、そのプレースホルダーのサイズと位置を計算し、その場所に [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] クロックを配置できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="ae1b8-172">RECT 四角形;</span><span class="sxs-lookup"><span data-stu-id="ae1b8-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="ae1b8-173">次に、プレースホルダーを静的に非表示にします。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="ae1b8-174">次のように、その場所に [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="ae1b8-175">このチュートリアルをおもしろいものにし、実際の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] クロックを作成するには、この時点で [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 時計コントロールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="ae1b8-176">多くの場合、コードビハインドでいくつかのイベントハンドラーを使用するだけで、マークアップでこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="ae1b8-177">このチュートリアルは相互運用に関するものであり、コントロールの設計に関するものではないため、ここでは [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] クロックの完全なコードをコードブロックとして提供しています。これは、ビルドのための個別の指示も、各部分が意味するものでもありません。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="ae1b8-178">このコードを自由に試して、コントロールの外観や外観を変更してください。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="ae1b8-179">マークアップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="ae1b8-180">次に、関連する分離コードを示します。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="ae1b8-181">最終的な結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-181">The final result looks like:</span></span>

![[最終結果の日付と時刻のプロパティ] ダイアログボックス](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="ae1b8-183">このスクリーンショットを生成したコードと結果を比較するには、「 [Win32 Clock 相互運用のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae1b8-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae1b8-184">参照</span><span class="sxs-lookup"><span data-stu-id="ae1b8-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="ae1b8-185">WPF と Win32 の相互運用性</span><span class="sxs-lookup"><span data-stu-id="ae1b8-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="ae1b8-186">Win32 クロック相互運用のサンプル</span><span class="sxs-lookup"><span data-stu-id="ae1b8-186">Win32 Clock Interoperation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32Clock)
