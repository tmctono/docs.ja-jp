---
title: インターネット インフォメーション サービスのホスティング手順
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: a537f37132e5014901d415cd96bc72a55ae0b750
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64600249"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="41865-102">インターネット インフォメーション サービスのホスティング手順</span><span class="sxs-lookup"><span data-stu-id="41865-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="41865-103">インターネット インフォメーション サービス (IIS) によってホストされているこのサンプルを実行するには、IIS が適切にインストールされて実行されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41865-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="41865-104">Windows Server 2008 R2 に IIS バージョン 7.5 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="41865-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="41865-105">**サーバー マネージャー**、**ロール。**</span><span class="sxs-lookup"><span data-stu-id="41865-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="41865-106">[**役割の概要**、] をクリックして**役割の追加**します。</span><span class="sxs-lookup"><span data-stu-id="41865-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="41865-107">をクリックして**次**を表示する、**サーバーの役割の選択**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="41865-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="41865-108">選択**アプリケーション サーバー**から、**ロール**ボックスの一覧をクリックして**次**を表示するには、2 回、**役割サービスの選択**ダイアログをアプリケーション サーバーの役割。</span><span class="sxs-lookup"><span data-stu-id="41865-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="41865-109">選択、 **Web サーバー (IIS)** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="41865-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="41865-110">追加の役割サービスと機能をインストールする場合は、クリックして**必要な機能を追加**します。</span><span class="sxs-lookup"><span data-stu-id="41865-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="41865-111">をクリックして**次**を表示するには、2 回、**役割サービスの選択**Web サーバー (IIS) ロールのダイアログ。</span><span class="sxs-lookup"><span data-stu-id="41865-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="41865-112">展開**管理ツール**、順に展開**IIS 6 管理互換**します。</span><span class="sxs-lookup"><span data-stu-id="41865-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="41865-113">選択**IIS 6 スクリプト ツール**します。</span><span class="sxs-lookup"><span data-stu-id="41865-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="41865-114">追加の役割サービスと機能をインストールする場合は、クリックして**必要な役割サービスの追加**します。</span><span class="sxs-lookup"><span data-stu-id="41865-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="41865-115">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41865-115">Click **Next**.</span></span>  
  
6. <span data-ttu-id="41865-116">選択内容が正しい場合は、クリックして**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="41865-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="41865-117">インストールが完了したら、クリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="41865-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="41865-118">Windows 7 に IIS バージョン 7.5 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="41865-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1. <span data-ttu-id="41865-119">クリックして**開始**、順にクリックします\*\*コントロール パネルの \*\*します。</span><span class="sxs-lookup"><span data-stu-id="41865-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="41865-120">開く、**プログラム**グループ。</span><span class="sxs-lookup"><span data-stu-id="41865-120">Open the **Programs** group.</span></span>  
  
3. <span data-ttu-id="41865-121">[**プログラムと機能**、] をクリックして**Windows 機能の有効化または無効**します。</span><span class="sxs-lookup"><span data-stu-id="41865-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="41865-122">**ユーザー アカウント制御**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41865-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="41865-123">**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41865-123">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="41865-124">**Windows 機能**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41865-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="41865-125">ラベル付き項目を展開**インターネット インフォメーション サービス**します。</span><span class="sxs-lookup"><span data-stu-id="41865-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="41865-126">ラベル付き項目を展開**World Wide Web サービス**します。</span><span class="sxs-lookup"><span data-stu-id="41865-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="41865-127">ラベル付き項目を展開**アプリケーション開発機能**します。</span><span class="sxs-lookup"><span data-stu-id="41865-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="41865-128">次の項目が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41865-128">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="41865-129">**.NET 拡張機能**</span><span class="sxs-lookup"><span data-stu-id="41865-129">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="41865-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="41865-130">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="41865-131">**ISAPI 拡張機能**</span><span class="sxs-lookup"><span data-stu-id="41865-131">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="41865-132">**ISAPI フィルター**</span><span class="sxs-lookup"><span data-stu-id="41865-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="41865-133">アイテムの下のラベル付け**World Wide Web サービス**、展開**Http 共通機能**します。</span><span class="sxs-lookup"><span data-stu-id="41865-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="41865-134">必ず**静的なコンテンツ**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="41865-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="41865-135">アイテムの下のラベル付け**World Wide Web サービス**、展開**セキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="41865-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="41865-136">必ず**Windows 認証**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="41865-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="41865-137">下、**インターネット インフォメーション サービス**ディレクトリ、ラベル付き項目を展開**Web 管理ツール**、し、 **IIS 管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="41865-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="41865-138">ラベル付き項目を展開**IIS 6 管理互換**、し、 **IIS 6 スクリプト ツール**します。</span><span class="sxs-lookup"><span data-stu-id="41865-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="41865-139">で、**インターネット インフォメーション サービス**ディレクトリ、ラベル付き項目を展開**Microsoft .NET Framework 3.5.1**、し、 **Windows Communication Foundation Http Activation**.</span><span class="sxs-lookup"><span data-stu-id="41865-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="41865-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41865-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="41865-141">Windows Server 2008 に IIS バージョン 7.0 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="41865-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1. <span data-ttu-id="41865-142">**サーバー マネージャー**、**ロール**します。</span><span class="sxs-lookup"><span data-stu-id="41865-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="41865-143">[**役割の概要**、] をクリックして**役割の追加**します。</span><span class="sxs-lookup"><span data-stu-id="41865-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="41865-144">をクリックして**次**を表示する、**サーバーの役割の選択**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="41865-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="41865-145">選択**アプリケーション サーバー**から、**ロール**ボックスの一覧をクリックして**次**を表示するには、2 回、**役割サービスの選択**ダイアログをアプリケーション サーバーの役割。</span><span class="sxs-lookup"><span data-stu-id="41865-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="41865-146">選択**Web サーバー (IIS)** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="41865-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="41865-147">追加の役割サービスと機能をインストールする場合は、クリックして**必要な機能を追加**します。</span><span class="sxs-lookup"><span data-stu-id="41865-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="41865-148">をクリックして**次**を表示するには、2 回、**役割サービスの選択**Web サーバー (IIS) ロールのダイアログ。</span><span class="sxs-lookup"><span data-stu-id="41865-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="41865-149">展開**管理ツール**、順に展開**IIS 6 管理互換**します。</span><span class="sxs-lookup"><span data-stu-id="41865-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="41865-150">選択**IIS 6 スクリプト ツール**します。</span><span class="sxs-lookup"><span data-stu-id="41865-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="41865-151">追加の役割サービスと機能をインストールする場合は、クリックして**必要な役割サービスの追加**します。</span><span class="sxs-lookup"><span data-stu-id="41865-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="41865-152">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41865-152">Click **Next**.</span></span>  
  
6. <span data-ttu-id="41865-153">選択内容が正しい場合は、クリックして**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="41865-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="41865-154">インストールが完了したら、クリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="41865-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="41865-155">Windows Vista に IIS バージョン 7.0 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="41865-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1. <span data-ttu-id="41865-156">[スタート] ボタンをクリックし、[コントロール パネル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41865-156">Click Start, and then click Control Panel.</span></span>  
  
2. <span data-ttu-id="41865-157">選択、**プログラム**グループ。</span><span class="sxs-lookup"><span data-stu-id="41865-157">Select the **Programs** group.</span></span>  
  
3. <span data-ttu-id="41865-158">[**プログラムと機能**、] をクリックして**Windows 機能の有効化または無効**します。</span><span class="sxs-lookup"><span data-stu-id="41865-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="41865-159">**ユーザー アカウント制御**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41865-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="41865-160">**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41865-160">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="41865-161">**Windows 機能**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41865-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="41865-162">ラベル付き項目を展開**インターネット インフォメーション サービス**します。</span><span class="sxs-lookup"><span data-stu-id="41865-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="41865-163">ラベル付き項目を展開**World Wide Web サービス**します。</span><span class="sxs-lookup"><span data-stu-id="41865-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="41865-164">ラベル付き項目を展開**アプリケーション開発機能**します。</span><span class="sxs-lookup"><span data-stu-id="41865-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="41865-165">次の項目が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41865-165">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="41865-166">**.NET 拡張機能**</span><span class="sxs-lookup"><span data-stu-id="41865-166">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="41865-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="41865-167">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="41865-168">**ISAPI 拡張機能**</span><span class="sxs-lookup"><span data-stu-id="41865-168">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="41865-169">**ISAPI フィルター**</span><span class="sxs-lookup"><span data-stu-id="41865-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="41865-170">ラベル付き項目を展開**Web 管理ツール**、し、 **IIS 管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="41865-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="41865-171">アイテムの下のラベル付け**World Wide Web サービス**、展開**Http 共通機能**します。</span><span class="sxs-lookup"><span data-stu-id="41865-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="41865-172">必ず**静的なコンテンツ**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="41865-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="41865-173">アイテムの下のラベル付け**World Wide Web サービス**、展開**セキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="41865-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="41865-174">必ず**Windows 認証**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="41865-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="41865-175">ラベル付き項目を展開**IIS 6 管理互換**、し、 **IIS 6 スクリプト ツール**します。</span><span class="sxs-lookup"><span data-stu-id="41865-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="41865-176">ラベル付き項目を展開**Microsoft .NET Framework 3.0**、し、 **Windows Communication Foundation Http Activation**します。</span><span class="sxs-lookup"><span data-stu-id="41865-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="41865-177">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41865-177">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="41865-178">Windows Server 2003 に IIS バージョン 6.0 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="41865-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1. <span data-ttu-id="41865-179">**サーバーの役割管理**、 をクリックして**追加または削除するロール**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="41865-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2. <span data-ttu-id="41865-180">選択**アプリケーション サーバー (IIS、ASP.NET)** から、**サーバーの役割**ボックスの一覧をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="41865-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="41865-181">選択**ASP.NET の有効化**チェック ボックスをオンにして**次**。</span><span class="sxs-lookup"><span data-stu-id="41865-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="41865-182">選択内容が正しい場合は、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41865-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="41865-183">Service Pack 2 および Service Pack 3 がインストールされている Windows XP に IIS バージョン 5.1 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="41865-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1. <span data-ttu-id="41865-184">コントロール パネルを開き、 **[プログラムの追加と削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41865-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2. <span data-ttu-id="41865-185">**プログラム追加と削除**ダイアログ ボックスで、をクリックして**Windows コンポーネントの追加/削除**します。</span><span class="sxs-lookup"><span data-stu-id="41865-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3. <span data-ttu-id="41865-186">**Windows コンポーネント ウィザード**を選択、**インターネット インフォメーション サービス (IIS)** チェック ボックスをオンにし**次**。</span><span class="sxs-lookup"><span data-stu-id="41865-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="41865-187">場合、**に必要なファイル** ダイアログ ボックスが表示されます、オペレーティング システムのインストール ディスクを挿入、i386 フォルダーを参照、および順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="41865-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="41865-188">インストールが完了したら、クリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="41865-188">When installation completes, click **Finish**.</span></span>  
  
6. <span data-ttu-id="41865-189">閉じる、**プログラム追加と削除**] ダイアログ ボックスを閉じます**コントロール パネルの [** します。</span><span class="sxs-lookup"><span data-stu-id="41865-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="41865-190">IIS と ASP.NET がインストールされていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="41865-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1. <span data-ttu-id="41865-191">このトピックの最後に示す HTML ファイルを \InetPub\wwwroot のルート ディレクトリに保存し、Default.aspx という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="41865-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2. <span data-ttu-id="41865-192">ブラウザー ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="41865-192">Open a browser window.</span></span>  
  
3. <span data-ttu-id="41865-193">型`http://localhost/Default.aspx`アドレス ボックスに、および ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="41865-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="41865-194">Web ページに、テキスト "Hello World" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41865-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41865-195">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] の新しいバージョンをインストールするたびに、IIS の Web サービス拡張として aspnet_isapi を再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41865-195">Each time you install a new version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="41865-196">これを行うには、`aspnet_regiis –I –enable` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41865-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="41865-197">サンプル コード</span><span class="sxs-lookup"><span data-stu-id="41865-197">Sample Code</span></span>  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
