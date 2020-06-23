---
title: '方法: MMC スナップインを使用して証明書を表示する'
description: セキュリティで保護された WCF クライアントまたはサービスでは、資格情報として証明書を使用できます。 MMC プラグインを使用して確認できる証明書ストアの種類について説明します。
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: e63034e48ae836f67f89b454829f7196c94610cd
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246676"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="8fdd6-104">方法: MMC スナップインを使用して証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="8fdd6-104">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="8fdd6-105">セキュリティで保護されたクライアントまたはサービスを作成する場合は、資格情報として[証明書](working-with-certificates.md)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-105">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="8fdd6-106">たとえば、一般的な資格情報の種類は、x.509 証明書です。この証明書は、メソッドを使用して作成します <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-106">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="8fdd6-107">Windows システムの Microsoft 管理コンソール (MMC) を使用して確認できる証明書ストアには、次の3種類があります。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-107">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="8fdd6-108">[ローカルコンピューター]: ストアはデバイスに対してローカルで、デバイス上のすべてのユーザーに対してグローバルです。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-108">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="8fdd6-109">現在のユーザー: ストアは、デバイス上の現在のユーザーアカウントに対してローカルです。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-109">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="8fdd6-110">サービスアカウント: ストアは、デバイス上の特定のサービスに対してローカルです。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-110">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="8fdd6-111">MMC スナップインで証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="8fdd6-111">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="8fdd6-112">次の手順では、ローカルデバイス上のストアを調べて、適切な証明書を検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-112">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="8fdd6-113">[**スタート**] メニューから [**実行**] を選択し、「 *mmc*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-113">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="8fdd6-114">MMC が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-114">The MMC appears.</span></span>
  
2. <span data-ttu-id="8fdd6-115">[**ファイル**] メニューの [**スナップインの追加と削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-115">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="8fdd6-116">[**スナップインの追加と削除**] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-116">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="8fdd6-117">[**利用できるスナップ**イン] の一覧から [**証明書**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-117">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![証明書スナップインの追加](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="8fdd6-119">[**証明書スナップ**イン] ウィンドウで、[**コンピューターアカウント**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-119">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="8fdd6-120">必要に応じて、特定のサービスの現在のユーザーまたは**サービスアカウント**の **[ユーザーアカウント**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-120">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8fdd6-121">デバイスの管理者でない場合は、自分のユーザーアカウントの証明書のみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-121">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="8fdd6-122">**[コンピューターの選択**] ウィンドウで、[**ローカルコンピューター** ] を選択したままにして、[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-122">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="8fdd6-123">[スナップインの**追加と削除**] ウィンドウで、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-123">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![証明書スナップインの追加](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="8fdd6-125">省略可能: [**ファイル**] メニューの [**保存**] または [**名前を付けて保存**] を選択すると、後で使用するために MMC コンソールファイルが保存されます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-125">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="8fdd6-126">MMC スナップインで証明書を表示するには、左側のウィンドウで [**コンソールルート**] を選択し、[**証明書 (ローカルコンピューター)**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-126">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="8fdd6-127">証明書の種類ごとにディレクトリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-127">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="8fdd6-128">各証明書ディレクトリから、証明書の表示、エクスポート、インポート、および削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-128">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="8fdd6-129">証明書マネージャーツールを使用して証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="8fdd6-129">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="8fdd6-130">証明書マネージャーツールを使用して、証明書の表示、エクスポート、インポート、および削除を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-130">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="8fdd6-131">ローカルデバイスの証明書を表示するには</span><span class="sxs-lookup"><span data-stu-id="8fdd6-131">To view certificates for the local device</span></span>

1. <span data-ttu-id="8fdd6-132">[**スタート**] メニューから [**実行**] を選択し、「 *certlm .msc*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-132">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="8fdd6-133">ローカルデバイスの証明書マネージャーツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-133">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="8fdd6-134">証明書を表示するには、左側のウィンドウの [**証明書-ローカルコンピューター** ] で、表示する証明書の種類のディレクトリを展開します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-134">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="8fdd6-135">現在のユーザーの証明書を表示するには</span><span class="sxs-lookup"><span data-stu-id="8fdd6-135">To view certificates for the current user</span></span>

1. <span data-ttu-id="8fdd6-136">**[スタート]** メニューから **[ファイル名を指定して実行]** メニューを選択し、「*certmgr.msc*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-136">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="8fdd6-137">現在のユーザーの証明書マネージャー ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-137">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="8fdd6-138">証明書を表示するには、左側のウィンドウの [**証明書-現在のユーザー** ] で、表示する証明書の種類のディレクトリを展開します。</span><span class="sxs-lookup"><span data-stu-id="8fdd6-138">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="8fdd6-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fdd6-139">See also</span></span>

- [<span data-ttu-id="8fdd6-140">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="8fdd6-140">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="8fdd6-141">方法: 開発時に使用する一時的な証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="8fdd6-141">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="8fdd6-142">方法: 証明書の拇印を取得する</span><span class="sxs-lookup"><span data-stu-id="8fdd6-142">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
