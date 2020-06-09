---
title: 仮想ディレクトリのセットアップ手順
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 2d9443431601ffc712da40bd1c085f595471336b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602363"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="6f606-102">仮想ディレクトリのセットアップ手順</span><span class="sxs-lookup"><span data-stu-id="6f606-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="6f606-103">Windows Communication Foundation (WCF) サンプルは、%SystemDrive%\inetpub\wwwroot\servicemodelsamples フォルダーにマップされている servicemodelsamples という名前の共通の仮想ディレクトリを共有することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="6f606-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f606-104">%SystemDrive% は、インターネット インフォメーション サービス (IIS) がインストールされているドライブの場所に応じて、通常は C: または D: になります。</span><span class="sxs-lookup"><span data-stu-id="6f606-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="6f606-105">[Windows Communication Foundation サンプルの1回限りのセットアップ手順](one-time-setup-procedure-for-the-wcf-samples.md)で、setupvroot と cleanupvroot ファイルを実行して、仮想ディレクトリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6f606-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="6f606-106">この仮想ディレクトリを手動で作成する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6f606-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="6f606-107">手順</span><span class="sxs-lookup"><span data-stu-id="6f606-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="6f606-108">IIS 7.0 または7.5 で仮想ディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="6f606-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="6f606-109">[**スタート**] メニューの [ファイルの**実行**] をクリックし、「 **inetmgr.exe** 」と入力して、インターネットインフォメーションサービス (IIS) MMC スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f606-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="6f606-110">左側のウィンドウで、コンピューターの名前のノードを展開し、[**サイト**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="6f606-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="6f606-111">[既定の**Web サイト**] を右クリックし、[**アプリケーションの追加**] を選択して [**アプリケーションの追加] ウィンドウ**を開きます。</span><span class="sxs-lookup"><span data-stu-id="6f606-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="6f606-112">ウィンドウで、作成する `servicemodelsamples` 仮想ディレクトリの別名として「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6f606-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="6f606-113">次のディレクトリを作成します。%SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="6f606-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="6f606-114">物理パスを %SystemDrive%\inetpub\wwwroot\servicemodelsamples に設定します。</span><span class="sxs-lookup"><span data-stu-id="6f606-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="6f606-115">WCF サンプルの多くは、ビルド時にサービス実行可能ファイルをこの場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6f606-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="6f606-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-116">Click **OK**.</span></span> <span data-ttu-id="6f606-117">Web アプリケーションが、WCF サンプル用に作成されました。</span><span class="sxs-lookup"><span data-stu-id="6f606-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6f606-118">すべての WCF サンプルで同じ servicemodelsamples Web アプリケーションが使用されるため、このタスクは1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f606-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6f606-119">このドキュメントでは、`virtual directory`という用語は `Web application`と同じ意味で使用しています。</span><span class="sxs-lookup"><span data-stu-id="6f606-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="6f606-120">仮想ディレクトリを作成するだけでなく、そのプロパティを設定して、WCF サービスを実行できるようにする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="6f606-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="6f606-121">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f606-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="6f606-122">仮想ディレクトリを IIS 5.1 または 6.0 で作成するには</span><span class="sxs-lookup"><span data-stu-id="6f606-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="6f606-123">コマンドプロンプトウィンドウを開き、「」と入力して `start inetmgr` 、インターネットインフォメーションサービス (IIS) MMC スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f606-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="6f606-124">左側のウィンドウで、コンピューターの名前のノードを展開し、[ **Web サイト**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="6f606-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="6f606-125">[既定の**Web サイト**] を右クリックし、[**新規]、[仮想ディレクトリ**] の順に選択して、仮想ディレクトリの作成ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f606-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="6f606-126">ウィザードで、作成する `servicemodelsamples` 仮想ディレクトリのエイリアスとして「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6f606-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="6f606-127">パスを %SystemDrive%\inetpub\wwwroot\servicemodelsamples に設定します。</span><span class="sxs-lookup"><span data-stu-id="6f606-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="6f606-128">WCF サンプルの多くは、ビルド時にサービス実行可能ファイルをこの場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6f606-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="6f606-129">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="6f606-130">既定では、次のチェック ボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="6f606-130">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="6f606-131">**読み取り**</span><span class="sxs-lookup"><span data-stu-id="6f606-131">**Read**</span></span>  
  
    - <span data-ttu-id="6f606-132">**[ASP などのスクリプトを実行する]**</span><span class="sxs-lookup"><span data-stu-id="6f606-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="6f606-133">[**次へ**] をクリックし、[**完了**] をクリックしてウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="6f606-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6f606-134">すべての WCF サンプルで同じ servicemodelsamples 仮想ディレクトリが使用されるため、このタスクは1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f606-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="6f606-135">IIS 7.0 または7.5 で追加の仮想ディレクトリプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="6f606-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="6f606-136">servicemodelsamples ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="6f606-137">ウィンドウの下端に沿って 2 つのビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f606-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="6f606-138">[**機能ビュー** ] を選択します (まだ選択されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="6f606-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="6f606-139">**ディレクトリ参照**のエントリをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="6f606-140">[操作] ウィンドウで、[**有効にする**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f606-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="6f606-141">これにより、Internet Explorer でディレクトリにアクセスできるようになり、サービスのデバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6f606-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="6f606-142">最後に、servicemodelsamples フォルダーのセキュリティ プロパティを、他のユーザーがアクセスできるように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f606-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="6f606-143">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f606-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="6f606-144">仮想ディレクトリの追加プロパティを IIS 5.1 または 6.0 で設定するには</span><span class="sxs-lookup"><span data-stu-id="6f606-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="6f606-145">[Servicemodelsamples] ノードを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="6f606-146">既定では、次のチェック ボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="6f606-146">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="6f606-147">**読み取り**</span><span class="sxs-lookup"><span data-stu-id="6f606-147">**Read**</span></span>  
  
    - <span data-ttu-id="6f606-148">**ログアクセス**</span><span class="sxs-lookup"><span data-stu-id="6f606-148">**Log visits**</span></span>  
  
    - <span data-ttu-id="6f606-149">**このリソースにインデックスを付けます**</span><span class="sxs-lookup"><span data-stu-id="6f606-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="6f606-150">[**ディレクトリの参照**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6f606-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="6f606-151">これにより、Internet Explorer でディレクトリにアクセスできるようになり、サービスのデバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6f606-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="6f606-152">IIS 7.0 または7.5 でフォルダーのセキュリティプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="6f606-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="6f606-153">%SystemDrive%\inetpub\wwwroot\servicemodelsamples に移動します。</span><span class="sxs-lookup"><span data-stu-id="6f606-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="6f606-154">Servicemodelsamples フォルダーを右クリックし、[**共有**] または [**共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="6f606-155">[**追加**] ボタンの左側にある下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="6f606-156">[**検索**] エントリを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f606-156">Select the **Find** entry.</span></span> <span data-ttu-id="6f606-157">**[ユーザーまたはグループの選択**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="6f606-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="6f606-158">**[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="6f606-159">[**場所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-159">Click **Locations**.</span></span> <span data-ttu-id="6f606-160">[**場所**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="6f606-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="6f606-161">使用するコンピューターのエントリを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f606-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="6f606-162">一覧表示されているドメインやネットワークのエントリではなく、ローカル コンピューターを選択してください。</span><span class="sxs-lookup"><span data-stu-id="6f606-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="6f606-163">コンピューターを選択したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="6f606-164">**[Find Now]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-164">Click **Find Now**.</span></span> <span data-ttu-id="6f606-165">これで、ローカル コンピューターに関連付けられたオブジェクトが検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f606-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="6f606-166">[**名前 (相対識別名)** ] 列で**IIS_IUSRS**エントリを探します。</span><span class="sxs-lookup"><span data-stu-id="6f606-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="6f606-167">そのエントリを選択し、[ **OK** ] をクリックして [検索結果] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f606-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="6f606-168">[ **OK]** をクリックして、[**ユーザーまたはグループの選択**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f606-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="6f606-169">変更を保持するには、[**共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="6f606-170">共有を有効にするための変更が完了したら、[**完了**] をクリックして [**ファイルの共有**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f606-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="6f606-171">フォルダーのセキュリティ プロパティを IIS 5.1 または 6.0 で設定するには</span><span class="sxs-lookup"><span data-stu-id="6f606-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="6f606-172">%SystemDrive%\inetpub\wwwroot\servicemodelsamples に移動します。</span><span class="sxs-lookup"><span data-stu-id="6f606-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="6f606-173">**Servicemodelsamples**フォルダーを右クリックし、[**共有とセキュリティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="6f606-174">**[セキュリティ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="6f606-175">IIS 6.0 を使用している場合は、[**グループ名またはユーザー名**] ボックスで、[**インターネットゲストアカウント**] が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f606-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="6f606-176">表示されていない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f606-176">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="6f606-177">**[スタート]** ボタンをクリックし、**コントロール パネル** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="6f606-178">[**ユーザーアカウント**] アイコンが表示されない場合は、[**カテゴリビューに切り替え] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="6f606-179">[**ユーザーアカウント**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-179">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="6f606-180">[コントロールパネルを選択してください] アイコンをクリックし、[**ユーザーアカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="6f606-181">[**ユーザーアカウント**] ダイアログボックスで、[**詳細設定**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="6f606-182">**[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-182">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="6f606-183">[**ローカルユーザーとグループ**] ダイアログボックスで、[**ユーザー** ] フォルダーをクリックして展開します。</span><span class="sxs-lookup"><span data-stu-id="6f606-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="6f606-184">右側のウィンドウで、[**インターネットゲストアカウント**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="6f606-185">[**プロパティ**] ダイアログボックスで、インターネットゲストアカウントとして使用されている名前をコピーします。</span><span class="sxs-lookup"><span data-stu-id="6f606-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="6f606-186">既定では、その名前は "USR_" で始まり、その次にコンピューターの名前が続きます。</span><span class="sxs-lookup"><span data-stu-id="6f606-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="6f606-187">**[プロパティ]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f606-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="6f606-188">[**ローカルユーザーとグループ**] ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f606-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="6f606-189">[**ユーザーアカウント**] ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f606-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="6f606-190">[その他の**ユーザーアカウント**] ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f606-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="6f606-191">[ **Servicemodelsamples のプロパティ**] ダイアログボックスの [**セキュリティ**] タブで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="6f606-192">コンピューターの名前とバックスラッシュを入力し、インターネットユーザーアカウントの名前を貼り付けます (例、myMachineName \\ % internetguestaccountname%)。</span><span class="sxs-lookup"><span data-stu-id="6f606-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="6f606-193">[**名前の確認**] をクリックして、追加を確認します。</span><span class="sxs-lookup"><span data-stu-id="6f606-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="6f606-194">名前が有効な場合は、すべての文字が下線付きの大文字になります。</span><span class="sxs-lookup"><span data-stu-id="6f606-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="6f606-195">IIS 6.0 の場合は、[**グループ名またはユーザー名**] ボックスに [ネットワークサービス] が表示されていることも確認します。</span><span class="sxs-lookup"><span data-stu-id="6f606-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="6f606-196">NETWORK SERVICE が表示されていない場合:</span><span class="sxs-lookup"><span data-stu-id="6f606-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="6f606-197">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-197">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="6f606-198">**[ユーザーまたはグループの選択**] ダイアログボックスで、コンピューター名の後にバックスラッシュを入力します。</span><span class="sxs-lookup"><span data-stu-id="6f606-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="6f606-199">バックスラッシュの後に「 **service** 」と入力します (スペースは不要です)。</span><span class="sxs-lookup"><span data-stu-id="6f606-199">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="6f606-200">[**名前の確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-200">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="6f606-201">複数の名前が見つかった場合は、[**ネットワークサービス**] を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="6f606-202">[ **OK** ] をクリックして、[**ユーザーまたはグループの選択**] ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f606-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="6f606-203">IIS 5.1 で Windows XP SP2 を使用している場合は、[**グループ名またはユーザー名**] ボックスに、インターネットゲストアカウントと ASPNET の両方が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f606-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="6f606-204">ASPNET ユーザーは、組み込みの**Users**セキュリティグループのメンバーである可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6f606-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="6f606-205">その場合、**ユーザー**グループがダイアログボックスに表示されている場合は、許可されたユーザーの一覧に個別のアイテムとして追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6f606-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="6f606-206">ASPNET が**Users**セキュリティグループに属しているかどうかを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f606-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="6f606-207">**[スタート]** ボタンをクリックし、 **[コントロール パネル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="6f606-208">[**ユーザーアカウント**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f606-208">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="6f606-209">[**グループ**] 列で、[ **ASPNET** ] の値が "Users" であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f606-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f606-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f606-210">See also</span></span>

- [<span data-ttu-id="6f606-211">インターネット インフォメーション サービスのホスティング手順</span><span class="sxs-lookup"><span data-stu-id="6f606-211">Internet Information Service Hosting Instructions</span></span>](internet-information-service-hosting-instructions.md)
