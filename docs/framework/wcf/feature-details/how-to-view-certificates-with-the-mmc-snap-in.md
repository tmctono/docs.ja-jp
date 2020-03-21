---
title: '方法: MMC スナップインを使用して証明書を表示する'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184777"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="49215-102">方法: MMC スナップインを使用して証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="49215-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="49215-103">セキュリティで保護されたクライアントまたはサービスを作成する場合、[証明書](working-with-certificates.md)を資格情報として使用できます。</span><span class="sxs-lookup"><span data-stu-id="49215-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="49215-104">たとえば、一般的な資格情報の種類は、メソッドで作成する X.509 証明書<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>です。</span><span class="sxs-lookup"><span data-stu-id="49215-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="49215-105">Windows システムの Microsoft 管理コンソール (MMC) で調べることができる証明書ストアには、次の 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="49215-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="49215-106">ローカル コンピューター: ストアはデバイスに対してローカルで、デバイス上のすべてのユーザーにグローバルです。</span><span class="sxs-lookup"><span data-stu-id="49215-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="49215-107">現在のユーザー: ストアは、デバイス上の現在のユーザー アカウントにローカルです。</span><span class="sxs-lookup"><span data-stu-id="49215-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="49215-108">サービス アカウント: ストアは、デバイス上の特定のサービスに対してローカルです。</span><span class="sxs-lookup"><span data-stu-id="49215-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="49215-109">MMC スナップインで証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="49215-109">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="49215-110">次の手順では、ローカル デバイス上のストアを調べて、適切な証明書を見つける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="49215-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="49215-111">**[スタート]** メニューから [ファイル名を**指定して実行**] を選択し、「 *mmc*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="49215-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="49215-112">MMC が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49215-112">The MMC appears.</span></span>
  
2. <span data-ttu-id="49215-113">[**ファイル]** メニューの [**スナップインの追加と削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49215-113">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="49215-114">[**スナップインの追加と削除**] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49215-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="49215-115">[**利用できるスナップイン**] ボックスの一覧で [**証明書**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49215-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![証明書スナップインの追加](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="49215-117">[**証明書スナップイン**] ウィンドウで、[コンピュータ**アカウント**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49215-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="49215-118">必要に応じて、現在**のユーザーに対して [ユーザー アカウント**] を選択するか、特定のサービスの**サービス アカウント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="49215-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="49215-119">デバイスの管理者でない場合は、自分のユーザー アカウントの証明書のみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="49215-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="49215-120">[**コンピュータの選択]** ウィンドウで、[**ローカル コンピュータ**] を選択したまま、[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49215-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="49215-121">[**スナップインの追加と削除**] ウィンドウで **、[OK] を**選択します。</span><span class="sxs-lookup"><span data-stu-id="49215-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![証明書スナップインの追加](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="49215-123">オプション: 「**ファイル」** メニューで、「**保存**」または「**名前を付けて保存**」を選択して、後で使用するために MMC コンソール・ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="49215-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="49215-124">MMC スナップインで証明書を表示するには、左側のウィンドウで **[コンソール ルート**] を選択し、[**証明書 (ローカル コンピュータ)]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="49215-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="49215-125">各種類の証明書のディレクトリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49215-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="49215-126">各証明書ディレクトリから、証明書の表示、エクスポート、インポート、および削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="49215-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="49215-127">証明書マネージャ ツールを使用して証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="49215-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="49215-128">証明書マネージャ ツールを使用して、証明書の表示、エクスポート、インポート、および削除を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="49215-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="49215-129">ローカル デバイスの証明書を表示するには</span><span class="sxs-lookup"><span data-stu-id="49215-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="49215-130">**[スタート]** メニューから [ファイル名を**指定して実行**] をクリックし *、「certlm.msc」* と入力します。</span><span class="sxs-lookup"><span data-stu-id="49215-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="49215-131">ローカル デバイスの証明書マネージャ ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49215-131">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="49215-132">証明書を表示するには、左側のウィンドウの [**証明書 - ローカル コンピューター** ] で、表示する証明書の種類のディレクトリを展開します。</span><span class="sxs-lookup"><span data-stu-id="49215-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="49215-133">現在のユーザーの証明書を表示するには</span><span class="sxs-lookup"><span data-stu-id="49215-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="49215-134">**[スタート]** メニューから [ファイル名を**指定して実行**] をクリックし *、certmgr.msc*と入力します。</span><span class="sxs-lookup"><span data-stu-id="49215-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="49215-135">現在のユーザーの証明書マネージャ ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49215-135">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="49215-136">証明書を表示するには、左側のウィンドウの [**証明書 - 現在のユーザー** ] の下で、表示する証明書の種類のディレクトリを展開します。</span><span class="sxs-lookup"><span data-stu-id="49215-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="49215-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="49215-137">See also</span></span>

- [<span data-ttu-id="49215-138">証明書の操作</span><span class="sxs-lookup"><span data-stu-id="49215-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="49215-139">方法: 開発中に使用する一時的な証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="49215-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="49215-140">方法: 証明書の拇印を取得する</span><span class="sxs-lookup"><span data-stu-id="49215-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
