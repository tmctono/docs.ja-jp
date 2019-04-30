---
title: Visual Studio では、DPI の認識を無効にします。
description: HDPI のモニターでの Windows フォーム デザイナーの制限事項と DPI に対応していないプロセスとして Visual Studio を実行する方法について説明します。
ms.date: 04/05/2019
ms.prod: visual-studio-windows
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
ms.custom: seoapril2019
ms.openlocfilehash: e52debea382033417afe0bd47f899af1666192bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967233"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a><span data-ttu-id="10a28-103">Visual Studio では、DPI の認識を無効にします。</span><span class="sxs-lookup"><span data-stu-id="10a28-103">Disable DPI-awareness in Visual Studio</span></span>

<span data-ttu-id="10a28-104">Visual Studio では、表示スケールを自動的に意味インチ (DPI) 対応アプリケーションあたりのドットです。</span><span class="sxs-lookup"><span data-stu-id="10a28-104">Visual Studio is a dots per inch (DPI) aware application, which means the display scales automatically.</span></span> <span data-ttu-id="10a28-105">アプリケーションでは、DPI 対応ではないことを示す、オペレーティング システムは、ビットマップとしてアプリケーションをスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="10a28-105">If an application states that it's not DPI-aware, the operating system scales the application as a bitmap.</span></span> <span data-ttu-id="10a28-106">この動作は、DPI の仮想化とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="10a28-106">This behavior is also called DPI virtualization.</span></span> <span data-ttu-id="10a28-107">アプリケーションは引き続き、100% に拡大縮小、または 96 dpi で実行されていると認識します。</span><span class="sxs-lookup"><span data-stu-id="10a28-107">The application still thinks that it's running at 100% scaling, or 96 dpi.</span></span>

<span data-ttu-id="10a28-108">この記事では、HDPI モニターでの Windows フォーム デザイナーの制限事項と DPI に対応していないプロセスとして Visual Studio を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10a28-108">This article discusses the limitations of Windows Forms Designer on HDPI monitors and how to run Visual Studio as a DPI-unaware process.</span></span>

## <a name="windows-forms-designer-on-hdpi-monitors"></a><span data-ttu-id="10a28-109">HDPI のモニターでの Windows フォーム デザイナー</span><span class="sxs-lookup"><span data-stu-id="10a28-109">Windows Forms Designer on HDPI monitors</span></span>

<span data-ttu-id="10a28-110">**Windows フォーム デザイナー** Visual Studio ではありませんスケーリングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="10a28-110">The **Windows Forms Designer** in Visual Studio doesn't have scaling support.</span></span> <span data-ttu-id="10a28-111">表示の問題は、一部のフォームを開いたときにこれにより、 **Windows フォーム デザイナー** high dots per インチ (HDPI) モニターです。</span><span class="sxs-lookup"><span data-stu-id="10a28-111">This causes display issues when you open some forms in the **Windows Forms Designer** on high dots per inch (HDPI) monitors.</span></span> <span data-ttu-id="10a28-112">例については、コントロールは、次の図のように重複する表示できます。</span><span class="sxs-lookup"><span data-stu-id="10a28-112">For examples, controls can appear to overlap as shown in the following image:</span></span>

![HDPI のモニターでの Windows フォーム デザイナー](./media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

<span data-ttu-id="10a28-114">フォームを開くと、 **Windows フォーム デザイナー** HDPI モニターで Visual Studio で、Visual Studio は、デザイナーの上部にある黄色のバーの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="10a28-114">When you open a form in the **Windows Forms Designer** in Visual Studio on an HDPI monitor, Visual Studio displays a yellow informational bar at the top of the designer:</span></span>

![DPI に対応していないモードで再起動する Visual Studio での情報バー](./media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

<span data-ttu-id="10a28-116">メッセージを読み取り**メイン ディスプレイのスケーリングを 200% (192 dpi) に設定します。デザイナー ウィンドウのレンダリングの問題があります。**</span><span class="sxs-lookup"><span data-stu-id="10a28-116">The message reads **Scaling on your main display is set to 200% (192 dpi). This might cause rendering problems in the designer window.**</span></span>

> [!NOTE]
> <span data-ttu-id="10a28-117">この情報バーは、Visual Studio 2017 バージョン 15.8 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="10a28-117">This informational bar was introduced in Visual Studio 2017 version 15.8.</span></span>

<span data-ttu-id="10a28-118">場合は、デザイナーを使用していないし、フォームのレイアウトを調整する必要はありません、情報バーを無視し、コード エディターまたはデザイナーの他の種類では、作業を続行できます。</span><span class="sxs-lookup"><span data-stu-id="10a28-118">If you aren't working in the designer and don't need to adjust the layout of your form, you can ignore the informational bar and continue working in the code editor or in other types of designers.</span></span> <span data-ttu-id="10a28-119">(することもできます[通知を無効にする](#disable-notifications)情報バーが表示され続けるようにします)。のみ、 **Windows フォーム デザイナー**が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="10a28-119">(You can also [disable notifications](#disable-notifications) so that the informational bar doesn't continue to appear.) Only the **Windows Forms Designer** is affected.</span></span> <span data-ttu-id="10a28-120">作業する必要がある場合、 **Windows フォーム デザイナー**、次のセクションでは[、問題を解決する](#to-resolve-the-display-problem)します。</span><span class="sxs-lookup"><span data-stu-id="10a28-120">If you do need to work in the **Windows Forms Designer**, the next section helps you [resolve the problem](#to-resolve-the-display-problem).</span></span>

## <a name="to-resolve-the-display-problem"></a><span data-ttu-id="10a28-121">表示に関する問題を解決するのには</span><span class="sxs-lookup"><span data-stu-id="10a28-121">To resolve the display problem</span></span>

<span data-ttu-id="10a28-122">表示に関する問題を解決するのには次の 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="10a28-122">There are three options to resolve the display problem:</span></span>

1. [<span data-ttu-id="10a28-123">DPI に対応していないプロセスとして Visual Studio を再起動します。</span><span class="sxs-lookup"><span data-stu-id="10a28-123">Restart Visual Studio as a DPI-unaware process</span></span>](#restart-visual-studio-as-a-dpi-unaware-process)
2. [<span data-ttu-id="10a28-124">レジストリ エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="10a28-124">Add a registry entry</span></span>](#add-a-registry-entry)
3. [<span data-ttu-id="10a28-125">設定、画面のスケーリングを 100% に設定します。</span><span class="sxs-lookup"><span data-stu-id="10a28-125">Set your display scaling setting to 100%</span></span>](#set-your-display-scaling-setting-to-100)

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a><span data-ttu-id="10a28-126">DPI に対応していないプロセスとして Visual Studio を再起動します。</span><span class="sxs-lookup"><span data-stu-id="10a28-126">Restart Visual Studio as a DPI-unaware process</span></span>

<span data-ttu-id="10a28-127">DPI に対応していないプロセスとして Visual Studio を再起動するには、黄色の情報バーのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="10a28-127">You can restart Visual Studio as a DPI-unaware process by selecting the option on the yellow informational bar.</span></span> <span data-ttu-id="10a28-128">これは、問題を解決することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10a28-128">This is the preferred way of resolving the problem.</span></span>

<span data-ttu-id="10a28-129">Visual Studio を DPI に対応していないプロセスとして実行すると、デザイナーのレイアウトの問題を解決するが、フォントがぼやけて表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10a28-129">When Visual Studio runs as a DPI-unaware process, the designer layout issues are resolved, but fonts may appear blurry.</span></span> <span data-ttu-id="10a28-130">Visual Studio は、ことを示す DPI に対応していないプロセスとして実行した場合に、別の黄色の情報メッセージを表示します**Visual Studio の DPI に対応していないプロセスとして実行します。WPF および XAML デザイナーが正しく表示されない場合があります。**</span><span class="sxs-lookup"><span data-stu-id="10a28-130">Visual Studio displays a different yellow informational message when it runs as a DPI-unaware process that says **Visual Studio is running as a DPI-unaware process. WPF and XAML designers might not display correctly.**</span></span> <span data-ttu-id="10a28-131">情報バーは、するためのオプションも用意されています。 **DPI 対応のプロセスとして Visual Studio を再起動**します。</span><span class="sxs-lookup"><span data-stu-id="10a28-131">The informational bar also provides an option to **Restart Visual Studio as a DPI-aware process**.</span></span>

> [!NOTE]
> - <span data-ttu-id="10a28-132">DPI に対応していないプロセスとして再起動するオプションを選択したときに、Visual Studio でツール ウィンドウをドッキング解除が、これらのツール ウィンドウの位置は変更可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10a28-132">If you had undocked tool windows in Visual Studio when you selected the option to restart as a DPI-unaware process, the position of those tool windows may change.</span></span>
> - <span data-ttu-id="10a28-133">既定の Visual Basic のプロファイルを使用する場合、またはがある場合、**作成時に新しいプロジェクトを保存**でオプションを選択解除**ツール** > **オプション** > **プロジェクトおよびソリューション**DPI に対応していないプロセスとして再起動するとき、Visual Studio がプロジェクトを再び開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="10a28-133">If you use the default Visual Basic profile, or if you have the **Save new projects when created** option deselected in **Tools** > **Options** > **Projects and Solutions**, Visual Studio cannot reopen your project when it restarts as a DPI-unaware process.</span></span> <span data-ttu-id="10a28-134">ただし、それを選択してプロジェクトを開く**ファイル** > **最近使ったプロジェクトおよびソリューション**します。</span><span class="sxs-lookup"><span data-stu-id="10a28-134">However, you can open the project by selecting it under **File** > **Recent Projects and Solutions**.</span></span>

<span data-ttu-id="10a28-135">作業が完了したら、DPI 対応のプロセスとして Visual Studio を再起動することが重要、 **Windows フォーム デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="10a28-135">It's important to restart Visual Studio as a DPI-aware process when you're finished working in the **Windows Forms Designer**.</span></span> <span data-ttu-id="10a28-136">DPI に対応していないプロセスとして実行されているフォントがぼやけてし、など他のデザイナーでの問題が発生する可能性があります、 **XAML デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="10a28-136">When it's running as a DPI-unaware process, fonts can look blurry and you may see issues in other designers such as the **XAML Designer**.</span></span> <span data-ttu-id="10a28-137">DPI に対応していないモードで実行されている Visual Studio を再度開くを起動する場合が DPI 対応もう一度です。</span><span class="sxs-lookup"><span data-stu-id="10a28-137">If you close and reopen Visual Studio when it's running in DPI-unaware mode, it becomes DPI-aware again.</span></span> <span data-ttu-id="10a28-138">クリックすることも、 **DPI 対応のプロセスとして Visual Studio を再起動**の情報バーのオプション。</span><span class="sxs-lookup"><span data-stu-id="10a28-138">You can also click the **Restart Visual Studio as a DPI-aware process** option in the informational bar.</span></span>

### <a name="add-a-registry-entry"></a><span data-ttu-id="10a28-139">レジストリ エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="10a28-139">Add a registry entry</span></span>

<span data-ttu-id="10a28-140">Visual Studio は、レジストリを変更して DPI 対応としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="10a28-140">You can mark Visual Studio as DPI-unaware by modifying the registry.</span></span> <span data-ttu-id="10a28-141">開いている**レジストリ エディター**にエントリを追加し、 **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers**サブキー。</span><span class="sxs-lookup"><span data-stu-id="10a28-141">Open **Registry Editor** and add an entry to the **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers** subkey:</span></span>

<span data-ttu-id="10a28-142">**エントリ**:かどうかを使用して Visual Studio 2017 または 2019 によってこれらの値のいずれかの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="10a28-142">**Entry**: Depending on whether you're using Visual Studio 2017 or 2019, use one of these values:</span></span>

- <span data-ttu-id="10a28-143">C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe</span><span class="sxs-lookup"><span data-stu-id="10a28-143">C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe</span></span>
- <span data-ttu-id="10a28-144">C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\devenv.exe</span><span class="sxs-lookup"><span data-stu-id="10a28-144">C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\devenv.exe</span></span>

> [!NOTE]
> <span data-ttu-id="10a28-145">Visual Studio の Professional または Enterprise edition を使用している場合は置き換えます**コミュニティ**で**Professional**または**Enterprise**エントリにします。</span><span class="sxs-lookup"><span data-stu-id="10a28-145">If you're using the Professional or Enterprise edition of Visual Studio, replace **Community** with **Professional** or **Enterprise** in the entry.</span></span> <span data-ttu-id="10a28-146">また、必要に応じて、ドライブ文字を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="10a28-146">Also replace the drive letter as necessary.</span></span>

<span data-ttu-id="10a28-147">**型**:REG_SZ</span><span class="sxs-lookup"><span data-stu-id="10a28-147">**Type**: REG_SZ</span></span>

<span data-ttu-id="10a28-148">**値**:DPIUNAWARE</span><span class="sxs-lookup"><span data-stu-id="10a28-148">**Value**: DPIUNAWARE</span></span>

> [!NOTE]
> <span data-ttu-id="10a28-149">Visual Studio は、レジストリ エントリを削除するまでに、DPI に対応していないモードでは残ります。</span><span class="sxs-lookup"><span data-stu-id="10a28-149">Visual Studio remains in DPI-unaware mode until you remove the registry entry.</span></span>

### <a name="set-your-display-scaling-setting-to-100"></a><span data-ttu-id="10a28-150">設定、画面のスケーリングを 100% に設定します。</span><span class="sxs-lookup"><span data-stu-id="10a28-150">Set your display scaling setting to 100%</span></span>

<span data-ttu-id="10a28-151">100% に設定を Windows 10 にスケールイン ディスプレイを設定する入力**表示設定**タスク バー、クリックして [検索] ボックスに**表示設定を変更**します。</span><span class="sxs-lookup"><span data-stu-id="10a28-151">To set your display scaling setting to 100% in Windows 10, type **display settings** in the task bar search box, and then select **Change display settings**.</span></span> <span data-ttu-id="10a28-152">**設定**ウィンドウで、設定**テキスト、アプリ、およびその他のアイテムのサイズを変更**に**100%** します。</span><span class="sxs-lookup"><span data-stu-id="10a28-152">In the **Settings** window, set **Change the size of text, apps, and other items** to **100%**.</span></span>

<span data-ttu-id="10a28-153">100% に拡大縮小、表示を設定できない可能性があります、ため、使用するのには小さすぎてユーザー インターフェイスをことができます。</span><span class="sxs-lookup"><span data-stu-id="10a28-153">Setting your display scaling to 100% may be undesirable, because it can make the user interface too small to be usable.</span></span>

## <a name="disable-notifications"></a><span data-ttu-id="10a28-154">通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="10a28-154">Disable notifications</span></span>

<span data-ttu-id="10a28-155">Visual Studio での問題のスケーリングの DPI 通知しないように選択できます。</span><span class="sxs-lookup"><span data-stu-id="10a28-155">You can choose not to be notified of DPI scaling issues in Visual Studio.</span></span> <span data-ttu-id="10a28-156">たとえば、デザイナーでしていない場合は通知を無効にする場合があります。</span><span class="sxs-lookup"><span data-stu-id="10a28-156">You might want to disable notifications if you aren't working in the designer, for example.</span></span>

<span data-ttu-id="10a28-157">通知を無効にする次のように選択します。**ツール** > **オプション**を開く、**オプション**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="10a28-157">To disable notifications, choose **Tools** > **Options** to open the **Options** dialog.</span></span> <span data-ttu-id="10a28-158">選択し、 **Windows フォーム デザイナー** > **全般**、設定と**DPI スケーリング通知**に**False**します。</span><span class="sxs-lookup"><span data-stu-id="10a28-158">Then, choose **Windows Forms Designer** > **General**, and set **DPI Scaling Notifications** to **False**.</span></span>

![DPI スケーリングに Visual Studio の通知オプション](./media/disable-dpi-awareness-visual-studio/notifications-option.png)

<span data-ttu-id="10a28-160">スケールの通知を後で再度有効にする場合、プロパティを設定**True**します。</span><span class="sxs-lookup"><span data-stu-id="10a28-160">If you want to later reenable scaling notifications, set the property to **True**.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="10a28-161">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="10a28-161">Troubleshoot</span></span>

<span data-ttu-id="10a28-162">DPI 対応の移行は、Visual Studio で期待どおりに動作していないの場合があるかどうかを確認、`dpiAwareness`値、 **hkey_local_machine \software\microsoft\windows nt \currentversion\image ファイル実行 Options\devenv.exe**サブキーのレジストリ エディターでします。</span><span class="sxs-lookup"><span data-stu-id="10a28-162">If the DPI-awareness transition isn't working as expected in Visual Studio, check to see if you have the `dpiAwareness` value in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\devenv.exe** subkey in Registry Editor.</span></span> <span data-ttu-id="10a28-163">存在する場合は、値を削除します。</span><span class="sxs-lookup"><span data-stu-id="10a28-163">Delete the value if it's present.</span></span>

## <a name="see-also"></a><span data-ttu-id="10a28-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="10a28-164">See also</span></span>

- [<span data-ttu-id="10a28-165">Windows フォームにおける自動スケーリング</span><span class="sxs-lookup"><span data-stu-id="10a28-165">Automatic scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
