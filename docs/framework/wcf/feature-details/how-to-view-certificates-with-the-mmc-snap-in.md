---
title: '方法: MMC スナップインで証明書の表示'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 6ec86ffca9ae84a9c3276a3dd6de676919dcd2e0
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200287"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="0dd41-102">方法: MMC スナップインで証明書の表示</span><span class="sxs-lookup"><span data-stu-id="0dd41-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="0dd41-103">使用することができますをセキュリティで保護されたクライアントまたはサービスを作成するときに、[証明書](working-with-certificates.md)資格情報として。</span><span class="sxs-lookup"><span data-stu-id="0dd41-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="0dd41-104">たとえば、資格情報の一般的な種類は、X.509 証明書を作成する、<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="0dd41-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span> 

<span data-ttu-id="0dd41-105">Windows システムで Microsoft 管理コンソール (MMC) とを確認する証明書ストアの 3 つの異なる種類があります。</span><span class="sxs-lookup"><span data-stu-id="0dd41-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="0dd41-106">ローカル コンピューターの場合:ストアは、デバイスのローカルと、デバイス上のすべてのユーザーにグローバルです。</span><span class="sxs-lookup"><span data-stu-id="0dd41-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="0dd41-107">現在のユーザー:ストアでは、デバイス上の現在のユーザー アカウントにローカルです。</span><span class="sxs-lookup"><span data-stu-id="0dd41-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="0dd41-108">サービス アカウント:ストアでは、デバイスの特定のサービスにローカルです。</span><span class="sxs-lookup"><span data-stu-id="0dd41-108">Service account: The store is local to a particular service on the device.</span></span>

  
## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="0dd41-109">MMC スナップインで証明書の表示</span><span class="sxs-lookup"><span data-stu-id="0dd41-109">View certificates in the MMC snap-in</span></span> 

<span data-ttu-id="0dd41-110">次の手順では、適切な証明書を検索するローカル デバイス上のストアを確認する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0dd41-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span> 
  
1. <span data-ttu-id="0dd41-111">選択**実行**から、**開始**] メニューの [し、入力*mmc*します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span> 

    <span data-ttu-id="0dd41-112">MMC が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dd41-112">The MMC appears.</span></span> 
  
2. <span data-ttu-id="0dd41-113">**ファイル**メニューの **スナップインの追加/削除**します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-113">From the **File** menu, select **Add/Remove Snap In**.</span></span> 
    
    <span data-ttu-id="0dd41-114">**スナップインを追加または**ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dd41-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="0dd41-115">**利用できるスナップイン**一覧で、選択**証明書**を選択し、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![証明書スナップインの追加します。](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="0dd41-117">**証明書スナップイン**ウィンドウで、**コンピューター アカウント**、し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span> 
  
    <span data-ttu-id="0dd41-118">必要に応じて、選択**ユーザー アカウント**、現在のユーザーまたは**サービス アカウント**特定のサービスです。</span><span class="sxs-lookup"><span data-stu-id="0dd41-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="0dd41-119">ない場合、管理者のデバイス、ユーザー アカウントに対してのみ証明書を管理できます。</span><span class="sxs-lookup"><span data-stu-id="0dd41-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="0dd41-120">**コンピューターの選択**] ウィンドウのままに**ローカル コンピューター**を選択し、[**完了**します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="0dd41-121">**スナップインの追加または削除**ウィンドウで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![証明書スナップインの追加します。](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="0dd41-123">省略可能:**ファイル**メニューの **保存**または**名前を付けて保存**後で使用できる MMC コンソール ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="0dd41-124">MMC スナップインで証明書を表示する選択**コンソール ルート**左側のウィンドウでを展開し、**証明書 (ローカル コンピューター)** します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="0dd41-125">証明書の種類ごとのディレクトリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dd41-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="0dd41-126">各証明書のディレクトリからすることができますを表示、エクスポート、インポート、およびその証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>
  

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="0dd41-127">証明書マネージャー ツールを使用して証明書の表示</span><span class="sxs-lookup"><span data-stu-id="0dd41-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="0dd41-128">ことができますも表示、エクスポート、インポート、および証明書マネージャー ツールを使用して証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="0dd41-129">ローカルのデバイス用の証明書を表示するには</span><span class="sxs-lookup"><span data-stu-id="0dd41-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="0dd41-130">選択**実行**から、**開始**] メニューの [し、入力*certlm.msc*します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span> 

    <span data-ttu-id="0dd41-131">ローカルのデバイスの証明書マネージャー ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dd41-131">The Certificate Manager tool for the local device appears.</span></span> 
  
2. <span data-ttu-id="0dd41-132">下に、証明書を表示する**証明書 - ローカル コンピューター**左側のウィンドウで表示する証明書の種類のディレクトリを展開します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="0dd41-133">現在のユーザーの証明書を表示するには</span><span class="sxs-lookup"><span data-stu-id="0dd41-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="0dd41-134">選択**実行**から、**開始**] メニューの [し、入力*certmgr.msc*します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span> 

    <span data-ttu-id="0dd41-135">現在のユーザーの証明書マネージャー ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dd41-135">The Certificate Manager tool for the current user appears.</span></span> 
  
2. <span data-ttu-id="0dd41-136">下に、証明書を表示する**証明書 - 現在のユーザー**左側のウィンドウで表示する証明書の種類のディレクトリを展開します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="0dd41-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dd41-137">See also</span></span>
- [<span data-ttu-id="0dd41-138">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="0dd41-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="0dd41-139">方法: 開発中に使用するための一時的な証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="0dd41-140">方法: 証明書のサムプリントを取得します。</span><span class="sxs-lookup"><span data-stu-id="0dd41-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
