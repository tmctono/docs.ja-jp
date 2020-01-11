---
title: ファイアウォール手順
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: 343fa695039f6767f6ab33daa4e3cc51e8db5e47
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899649"
---
# <a name="firewall-instructions"></a><span data-ttu-id="e3a7a-102">ファイアウォールの手順</span><span class="sxs-lookup"><span data-stu-id="e3a7a-102">Firewall instructions</span></span>

<span data-ttu-id="e3a7a-103">Windows Communication Foundation (WCF) サンプルを機能させるには、ファイアウォールで複数のポートまたはプログラムを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="e3a7a-104">サンプルの多くは、通信する際に 8000 ～ 8003 の範囲のポートと 9000 のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="e3a7a-105">既定ではファイアウォールが有効なので、こうしたポートにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="e3a7a-106">サンプル用にファイアウォールを有効にするには、要件とセキュリティ環境に応じて次のいずれかの手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>

- <span data-ttu-id="e3a7a-107">オプション 1: 実行中のサンプルを対話形式で有効にします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="e3a7a-108">ファイアウォールの構成をあらかじめ変更することなく、サンプルのビルドおよび実行の開始に進みます。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="e3a7a-109">サンプルを実行すると、 **[Windows セキュリティ警告]** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="e3a7a-110">対象のプログラムを、ブロック解除の一覧に対話形式で追加できます。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="e3a7a-111">この手順では、この後サンプルを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-111">With this procedure, you may have to then restart the sample.</span></span>

- <span data-ttu-id="e3a7a-112">オプション 2: サンプル プログラムをあらかじめ有効にしておきます。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="e3a7a-113">**Windows ファイアウォールのコントロールパネル**アプレットを起動し、実行する予定のサンプルプログラムを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="e3a7a-114">実行可能ファイルが存在するように、プログラムを最初にビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="e3a7a-115">手順の詳細については、後述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-115">You can find more detailed instructions in the following procedure.</span></span>

- <span data-ttu-id="e3a7a-116">オプション 3: ポート範囲をあらかじめ有効にしておきます。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="e3a7a-117">**Windows ファイアウォールのコントロールパネル**アプレットを起動し、サンプルで使用されるポート80、443、8000-8003、9000を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-117">Start the **Windows Firewall Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="e3a7a-118">手順の詳細については、後述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="e3a7a-119">このオプションは他の手順よりも安全性が低くなります。サンプルだけでなく、任意のプログラムでこれらのポートを使用できるようになるからです。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>

<span data-ttu-id="e3a7a-120">どの手順を使用するか判断に迷う場合は、最初のオプションを選択してください。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="e3a7a-121">他のベンダのファイアウォールを実行している場合も、同様の変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3a7a-122">ファイアウォールの構成を変更すると、セキュリティに影響します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="e3a7a-123">変更内容は記録し、サンプルの使用が終わったらそれらの変更点を削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>

## <a name="enable-samples-programs-in-advance"></a><span data-ttu-id="e3a7a-124">サンプルプログラムを事前に有効にする</span><span class="sxs-lookup"><span data-stu-id="e3a7a-124">Enable samples programs in advance</span></span>

1. <span data-ttu-id="e3a7a-125">このサンプルをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-125">Build the sample.</span></span>

2. <span data-ttu-id="e3a7a-126">[**開始** > **実行**] を選択し、「`firewall.cpl`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-126">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="e3a7a-127">これにより、[ **Windows ファイアウォール] コントロールパネル**アプレットが開きます。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-127">This opens the **Windows Firewall Control Panel** applet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3a7a-128">Windows ファイアウォールを介して通信する機能が必要なサンプルを実行するには、ファイアウォール設定を変更するための権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="e3a7a-129">一部のファイウォール設定を変更できず、コンピューターがドメインに接続される場合は、システム管理者がグループ ポリシーを使用してファイアウォール設定を管理している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>

3. <span data-ttu-id="e3a7a-130">Windows ファイアウォール経由でプログラムを許可するには、次のいずれかの操作固有の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-130">Complete one of the following operating-specific steps to allow a program through the Windows Firewall:</span></span>

    - <span data-ttu-id="e3a7a-131">Windows 7 または Windows Server 2008 R2 で、[ **Windows ファイアウォールを介したプログラムまたは機能を許可**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-131">On Windows 7 or Windows Server 2008 R2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="e3a7a-132">**[設定の変更]** をクリックして、**別のプログラム > 許可**します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-132">Click **Change Settings** > **Allow Another Program**.</span></span>

    - <span data-ttu-id="e3a7a-133">Windows Vista または Windows Server 2008 の場合は、 **[Windows ファイアウォールによるプログラムの許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-133">On Windows Vista or Windows Server 2008, click **Allow a program through Windows Firewall**.</span></span>

4. <span data-ttu-id="e3a7a-134">**[例外]** タブで、 **[プログラムの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-134">On the **Exceptions** tab, click **Add Program**.</span></span>

5. <span data-ttu-id="e3a7a-135">**参照**ボタンをクリックし、実行するサンプルの実行可能ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>

6. <span data-ttu-id="e3a7a-136">実行する予定のすべてのサンプルの実行可能ファイルを追加するまで、手順4と5を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>

7. <span data-ttu-id="e3a7a-137">[ **OK]** をクリックして、ファイアウォールアプレットを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-137">Click **OK** to close the firewall applet.</span></span>

## <a name="enable-a-port-range-in-advance"></a><span data-ttu-id="e3a7a-138">ポート範囲を事前に有効にする</span><span class="sxs-lookup"><span data-stu-id="e3a7a-138">Enable a port range in advance</span></span>

1. <span data-ttu-id="e3a7a-139">[**開始** > **実行**] を選択し、「`firewall.cpl`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-139">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="e3a7a-140">これにより、[ **Windows ファイアウォール] コントロールパネル**アプレットが開きます。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-140">This opens the **Windows Firewall Control Panel** applet.</span></span>

2. <span data-ttu-id="e3a7a-141">Windows 7 または Windows Server 2008 R2 の場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>

    1. <span data-ttu-id="e3a7a-142">Windows ファイアウォール ウィンドウの左側の列にある **詳細設定** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>

    2. <span data-ttu-id="e3a7a-143">左側の列の **[受信の規則]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-143">Click **Inbound Rules** in the left column.</span></span>

    3. <span data-ttu-id="e3a7a-144">右側の列で **[新しいルール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-144">Click **New Rules** in the right column.</span></span>

    4. <span data-ttu-id="e3a7a-145">**[ポート]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-145">Select **Port** and click **next**.</span></span>

    5. <span data-ttu-id="e3a7a-146">**[TCP]** を選択し、 **[特定のローカルポート]** フィールドに「`8000, 8001, 8002, 8003, 9000, 80, 443`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>

    6. <span data-ttu-id="e3a7a-147">[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-147">Click **Next**.</span></span>

    7. <span data-ttu-id="e3a7a-148">**[接続を許可する]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-148">Select **Allow the connection**, and click **Next** .</span></span>

    8. <span data-ttu-id="e3a7a-149">[**ドメイン**と**プライベート**] を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-149">Select **Domain** and **Private**, and click **Next**.</span></span>

    9. <span data-ttu-id="e3a7a-150">この規則 `WCF-WF 4.0 Samples`という名前を指定し、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>

    10. <span data-ttu-id="e3a7a-151">**[送信の規則]** をクリックし、手順 c ~ h を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-151">Click **Outbound Rules** and repeat steps c to h.</span></span>

3. <span data-ttu-id="e3a7a-152">Windows Vista または Windows Server 2008 では、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-152">On Windows Vista or Windows Server 2008, follow these steps.</span></span>

    1. <span data-ttu-id="e3a7a-153">**[Windows ファイアウォールによるプログラムの許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-153">Click **Allow a program through Windows Firewall**.</span></span>

    2. <span data-ttu-id="e3a7a-154">**[例外]** タブで、 **[ポートの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-154">On the **Exceptions** tab, click **Add Port**.</span></span>

    3. <span data-ttu-id="e3a7a-155">名前を入力し、ポート番号として「8000」と入力して、 **[TCP]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>

    4. <span data-ttu-id="e3a7a-156">**[スコープの変更]** ボタンをクリックし、 **[マイネットワーク]** (サブネット) のみ オプションを選択して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>

    5. <span data-ttu-id="e3a7a-157">手順 b ～ d を繰り返して、ポート 8001、8002、8003、9000、80、および 443 を設定します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>

4. <span data-ttu-id="e3a7a-158">[ **OK]** をクリックして、ファイアウォールアプレットを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-158">Click **OK** to close the firewall applet.</span></span>

> [!NOTE]
> <span data-ttu-id="e3a7a-159">サンプルの実行が終わったら、ファイアウォールのすべての例外を削除します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="e3a7a-160">これを行うには、[ **Windows ファイアウォール] コントロールパネル**アプレットを開き、前の手順で追加したプログラムまたはポートエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="e3a7a-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
