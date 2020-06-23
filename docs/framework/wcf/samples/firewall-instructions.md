---
title: ファイアウォール手順
description: ファイアウォールで WCF サンプル用のポートまたはプログラムを有効にする方法について説明します。 要件とセキュリティ環境に応じて、次のいずれかの手順を使用します。
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: de55d067960b8f2096c129f6feaf037219e06a96
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246142"
---
# <a name="firewall-instructions"></a><span data-ttu-id="3238c-104">ファイアウォールの手順</span><span class="sxs-lookup"><span data-stu-id="3238c-104">Firewall instructions</span></span>

<span data-ttu-id="3238c-105">Windows Communication Foundation (WCF) サンプルを機能させるには、ファイアウォールで複数のポートまたはプログラムを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3238c-105">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="3238c-106">サンプルの多くは、通信する際に 8000 ～ 8003 の範囲のポートと 9000 のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="3238c-106">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="3238c-107">既定ではファイアウォールが有効なので、こうしたポートにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="3238c-107">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="3238c-108">サンプル用にファイアウォールを有効にするには、要件とセキュリティ環境に応じて次のいずれかの手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3238c-108">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>

- <span data-ttu-id="3238c-109">オプション 1: 実行中のサンプルを対話形式で有効にします。</span><span class="sxs-lookup"><span data-stu-id="3238c-109">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="3238c-110">ファイアウォールの構成をあらかじめ変更することなく、サンプルのビルドおよび実行の開始に進みます。</span><span class="sxs-lookup"><span data-stu-id="3238c-110">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="3238c-111">サンプルを実行すると、[ **Windows セキュリティ警告**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3238c-111">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="3238c-112">対象のプログラムを、ブロック解除の一覧に対話形式で追加できます。</span><span class="sxs-lookup"><span data-stu-id="3238c-112">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="3238c-113">この手順では、この後サンプルを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3238c-113">With this procedure, you may have to then restart the sample.</span></span>

- <span data-ttu-id="3238c-114">オプション 2: サンプル プログラムをあらかじめ有効にしておきます。</span><span class="sxs-lookup"><span data-stu-id="3238c-114">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="3238c-115">**Windows ファイアウォールのコントロールパネル**アプレットを起動し、実行する予定のサンプルプログラムを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3238c-115">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="3238c-116">実行可能ファイルが存在するように、プログラムを最初にビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3238c-116">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="3238c-117">手順の詳細については、後述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3238c-117">You can find more detailed instructions in the following procedure.</span></span>

- <span data-ttu-id="3238c-118">オプション 3: ポート範囲をあらかじめ有効にしておきます。</span><span class="sxs-lookup"><span data-stu-id="3238c-118">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="3238c-119">**Windows ファイアウォールのコントロールパネル**アプレットを起動し、サンプルで使用されるポート80、443、8000-8003、9000を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3238c-119">Start the **Windows Firewall Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="3238c-120">手順の詳細については、後述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3238c-120">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="3238c-121">このオプションは他の手順よりも安全性が低くなります。サンプルだけでなく、任意のプログラムでこれらのポートを使用できるようになるからです。</span><span class="sxs-lookup"><span data-stu-id="3238c-121">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>

<span data-ttu-id="3238c-122">どの手順を使用するか判断に迷う場合は、最初のオプションを選択してください。</span><span class="sxs-lookup"><span data-stu-id="3238c-122">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="3238c-123">他のベンダのファイアウォールを実行している場合も、同様の変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3238c-123">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3238c-124">ファイアウォールの構成を変更すると、セキュリティに影響します。</span><span class="sxs-lookup"><span data-stu-id="3238c-124">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="3238c-125">変更内容は記録し、サンプルの使用が終わったらそれらの変更点を削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3238c-125">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>

## <a name="enable-samples-programs-in-advance"></a><span data-ttu-id="3238c-126">サンプルプログラムを事前に有効にする</span><span class="sxs-lookup"><span data-stu-id="3238c-126">Enable samples programs in advance</span></span>

1. <span data-ttu-id="3238c-127">サンプルをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3238c-127">Build the sample.</span></span>

2. <span data-ttu-id="3238c-128">[ **Start**  >  **実行**の開始] を選択し、「」と入力し `firewall.cpl` ます。</span><span class="sxs-lookup"><span data-stu-id="3238c-128">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="3238c-129">これにより、[ **Windows ファイアウォール] コントロールパネル**アプレットが開きます。</span><span class="sxs-lookup"><span data-stu-id="3238c-129">This opens the **Windows Firewall Control Panel** applet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3238c-130">Windows ファイアウォールを介して通信する機能が必要なサンプルを実行するには、ファイアウォール設定を変更するための権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="3238c-130">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="3238c-131">一部のファイウォール設定を変更できず、コンピューターがドメインに接続される場合は、システム管理者がグループ ポリシーを使用してファイアウォール設定を管理している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3238c-131">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>

3. <span data-ttu-id="3238c-132">Windows ファイアウォール経由でプログラムを許可するには、次のいずれかの操作固有の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3238c-132">Complete one of the following operating-specific steps to allow a program through the Windows Firewall:</span></span>

    - <span data-ttu-id="3238c-133">Windows 7 または Windows Server 2008 R2 で、[ **Windows ファイアウォールを介したプログラムまたは機能を許可**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-133">On Windows 7 or Windows Server 2008 R2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="3238c-134">[**設定の変更**] [  >  **別のプログラムの許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-134">Click **Change Settings** > **Allow Another Program**.</span></span>

    - <span data-ttu-id="3238c-135">Windows Vista または Windows Server 2008 の場合は、[ **Windows ファイアウォールによるプログラムの許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-135">On Windows Vista or Windows Server 2008, click **Allow a program through Windows Firewall**.</span></span>

4. <span data-ttu-id="3238c-136">[**例外**] タブで、[**プログラムの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-136">On the **Exceptions** tab, click **Add Program**.</span></span>

5. <span data-ttu-id="3238c-137">**参照**ボタンをクリックし、実行するサンプルの実行可能ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3238c-137">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>

6. <span data-ttu-id="3238c-138">実行する予定のすべてのサンプルの実行可能ファイルを追加するまで、手順4と5を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3238c-138">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>

7. <span data-ttu-id="3238c-139">[ **OK]** をクリックして、ファイアウォールアプレットを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3238c-139">Click **OK** to close the firewall applet.</span></span>

## <a name="enable-a-port-range-in-advance"></a><span data-ttu-id="3238c-140">ポート範囲を事前に有効にする</span><span class="sxs-lookup"><span data-stu-id="3238c-140">Enable a port range in advance</span></span>

1. <span data-ttu-id="3238c-141">[ **Start**  >  **実行**の開始] を選択し、「」と入力し `firewall.cpl` ます。</span><span class="sxs-lookup"><span data-stu-id="3238c-141">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="3238c-142">これにより、[ **Windows ファイアウォール] コントロールパネル**アプレットが開きます。</span><span class="sxs-lookup"><span data-stu-id="3238c-142">This opens the **Windows Firewall Control Panel** applet.</span></span>

2. <span data-ttu-id="3238c-143">Windows 7 または Windows Server 2008 R2 の場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3238c-143">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>

    1. <span data-ttu-id="3238c-144">[Windows ファイアウォール] ウィンドウの左側の列にある [**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-144">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>

    2. <span data-ttu-id="3238c-145">左側の列の [**受信の規則**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-145">Click **Inbound Rules** in the left column.</span></span>

    3. <span data-ttu-id="3238c-146">右側の列で [**新しいルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-146">Click **New Rules** in the right column.</span></span>

    4. <span data-ttu-id="3238c-147">[**ポート**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-147">Select **Port** and click **next**.</span></span>

    5. <span data-ttu-id="3238c-148">[ **TCP** ] を選択し `8000, 8001, 8002, 8003, 9000, 80, 443` 、[特定の**ローカルポート**] フィールドに「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3238c-148">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>

    6. <span data-ttu-id="3238c-149">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-149">Click **Next**.</span></span>

    7. <span data-ttu-id="3238c-150">[**接続を許可する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-150">Select **Allow the connection**, and click **Next** .</span></span>

    8. <span data-ttu-id="3238c-151">[**ドメイン**と**プライベート**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-151">Select **Domain** and **Private**, and click **Next**.</span></span>

    9. <span data-ttu-id="3238c-152">このルール `WCF-WF 4.0 Samples` に名前を指定し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-152">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>

    10. <span data-ttu-id="3238c-153">[**送信の規則**] をクリックし、手順 c ~ h を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3238c-153">Click **Outbound Rules** and repeat steps c to h.</span></span>

3. <span data-ttu-id="3238c-154">Windows Vista または Windows Server 2008 では、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3238c-154">On Windows Vista or Windows Server 2008, follow these steps.</span></span>

    1. <span data-ttu-id="3238c-155">**[Windows ファイアウォールによるプログラムの許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-155">Click **Allow a program through Windows Firewall**.</span></span>

    2. <span data-ttu-id="3238c-156">[**例外**] タブで、[**ポートの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-156">On the **Exceptions** tab, click **Add Port**.</span></span>

    3. <span data-ttu-id="3238c-157">名前を入力し、ポート番号として「8000」と入力して、[ **TCP** ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3238c-157">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>

    4. <span data-ttu-id="3238c-158">[**スコープの変更**] ボタンをクリックし、[**マイネットワーク**(サブネット) のみ] オプションを選択して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3238c-158">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>

    5. <span data-ttu-id="3238c-159">手順 b ～ d を繰り返して、ポート 8001、8002、8003、9000、80、および 443 を設定します。</span><span class="sxs-lookup"><span data-stu-id="3238c-159">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>

4. <span data-ttu-id="3238c-160">[ **OK]** をクリックして、ファイアウォールアプレットを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3238c-160">Click **OK** to close the firewall applet.</span></span>

> [!NOTE]
> <span data-ttu-id="3238c-161">サンプルの実行が終わったら、ファイアウォールのすべての例外を削除します。</span><span class="sxs-lookup"><span data-stu-id="3238c-161">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="3238c-162">これを行うには、[ **Windows ファイアウォール] コントロールパネル**アプレットを開き、前の手順で追加したプログラムまたはポートエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="3238c-162">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
