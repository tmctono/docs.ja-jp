---
title: '方法: 証明書のサムプリントを取得する'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], retrieving thumbprint
ms.assetid: da3101aa-78cd-4c34-9652-d1f24777eeab
ms.openlocfilehash: 51debbbcfec2fd5b82460e1dd1d6ece8e77bfc13
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307757"
---
# <a name="how-to-retrieve-the-thumbprint-of-a-certificate"></a><span data-ttu-id="d2740-102">方法: 証明書のサムプリントを取得する</span><span class="sxs-lookup"><span data-stu-id="d2740-102">How to: Retrieve the Thumbprint of a Certificate</span></span>
<span data-ttu-id="d2740-103">認証に X.509 証明書を使用する Windows Communication Foundation (WCF) アプリケーションを作成する場合、要求にある証明書を指定する必要は多くの場合。</span><span class="sxs-lookup"><span data-stu-id="d2740-103">When writing a Windows Communication Foundation (WCF) application that uses an X.509 certificate for authentication, it is often necessary to specify claims found in the certificate.</span></span> <span data-ttu-id="d2740-104">たとえば、 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> メソッドで <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 列挙体を使用する場合は、拇印クレームを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2740-104">For example, you must supply a thumbprint claim when using the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> enumeration in the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="d2740-105">クレーム値を検索するには 2 つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2740-105">Finding the claim value requires two steps.</span></span> <span data-ttu-id="d2740-106">まず、証明書用の Microsoft 管理コンソール (MMC) スナップインを開きます</span><span class="sxs-lookup"><span data-stu-id="d2740-106">First, open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="d2740-107">(「[方法: MMC スナップインで証明書を表示](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md))。次に、ここで説明されているとおりに適切な証明書を検索してその拇印 (または他のクレーム値) をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d2740-107">(See [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).) Second, as described here, find an appropriate certificate and copy its thumbprint (or other claim values).</span></span>  
  
 <span data-ttu-id="d2740-108">サービス認証で証明書を使用する場合は、 **[Issued To]** 列 (コンソールの 1 番目の列) の値に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d2740-108">If you are using a certificate for service authentication, it is important to note the value of the **Issued To** column (the first column in the console).</span></span> <span data-ttu-id="d2740-109">トランスポート セキュリティとして SSL (Secure Sockets Layer) を使用する場合、実行される最初のチェックの 1 つで、サービスのベース アドレス URI (Uniform Resource Identifier) が **[Issued To]** の値と比較されます。</span><span class="sxs-lookup"><span data-stu-id="d2740-109">When using Secure Sockets Layer (SSL) as a transport security, one of the first checks done is to compare the base address Uniform Resource Identifier (URI) of a service to the **Issued To** value.</span></span> <span data-ttu-id="d2740-110">値は一致する必要があります。一致しない場合は、認証が停止します。</span><span class="sxs-lookup"><span data-stu-id="d2740-110">The values must match or the authentication process is halted.</span></span>  
  
 <span data-ttu-id="d2740-111">開発時にのみ使用するための一時的な証明書を作成する Powershell New-selfsignedcertificate コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d2740-111">You can also use the Powershell New-SelfSignedCertificate cmdlet to create temporary certificates for use only during development.</span></span> <span data-ttu-id="d2740-112">既定では、ただし、このような証明書は証明機関から発行されないとは運用環境では使用できません。</span><span class="sxs-lookup"><span data-stu-id="d2740-112">By default, however, such a certificate is not issued by a certification authority and is unusable for production purposes.</span></span> <span data-ttu-id="d2740-113">詳細については、「[方法 :開発中に使用するための一時的な証明書を作成](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)です。</span><span class="sxs-lookup"><span data-stu-id="d2740-113">For more information, see [How to: Create Temporary Certificates for Use During Development](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).</span></span>  
  
### <a name="to-retrieve-a-certificates-thumbprint"></a><span data-ttu-id="d2740-114">証明書の拇印を取得するには</span><span class="sxs-lookup"><span data-stu-id="d2740-114">To retrieve a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="d2740-115">証明書用の Microsoft 管理コンソール (MMC) スナップインを開きます</span><span class="sxs-lookup"><span data-stu-id="d2740-115">Open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="d2740-116">(「[方法: MMC スナップインで証明書を表示](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md))。</span><span class="sxs-lookup"><span data-stu-id="d2740-116">(See [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).)</span></span>  
  
2. <span data-ttu-id="d2740-117">**[Console Root]** ウィンドウの左ペインで、 **[Certificates (Local Computer)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2740-117">In the **Console Root** window's left pane, click **Certificates (Local Computer)**.</span></span>  
  
3. <span data-ttu-id="d2740-118">**[Personal]** フォルダーをクリックして展開します。</span><span class="sxs-lookup"><span data-stu-id="d2740-118">Click the **Personal** folder to expand it.</span></span>  
  
4. <span data-ttu-id="d2740-119">**[Certificates]** フォルダーをクリックして展開します。</span><span class="sxs-lookup"><span data-stu-id="d2740-119">Click the **Certificates** folder to expand it.</span></span>  
  
5. <span data-ttu-id="d2740-120">証明書リストの **[Intended Purposes]** 見出しを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2740-120">In the list of certificates, note the **Intended Purposes** heading.</span></span> <span data-ttu-id="d2740-121">目的として **[Client Authentication]** が表示されている証明書を検索します。</span><span class="sxs-lookup"><span data-stu-id="d2740-121">Find a certificate that lists **Client Authentication** as an intended purpose.</span></span>  
  
6. <span data-ttu-id="d2740-122">証明書をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2740-122">Double-click the certificate.</span></span>  
  
7. <span data-ttu-id="d2740-123">**[Certificate]** ダイアログ ボックスの **[Details]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2740-123">In the **Certificate** dialog box, click the **Details** tab.</span></span>  
  
8. <span data-ttu-id="d2740-124">フィールド リストをスクロールし、 **[Thumbprint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2740-124">Scroll through the list of fields and click **Thumbprint**.</span></span>  
  
9. <span data-ttu-id="d2740-125">ボックスから 16 進文字をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d2740-125">Copy the hexadecimal characters from the box.</span></span> <span data-ttu-id="d2740-126">この拇印を `X509FindType`のコードで使用する場合は、16 進文字の間のスペースを削除します。</span><span class="sxs-lookup"><span data-stu-id="d2740-126">If this thumbprint is used in code for the `X509FindType`, remove the spaces between the hexadecimal numbers.</span></span> <span data-ttu-id="d2740-127">たとえば、拇印 "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b" は、コード内で "a909502dd82ae41433e6f83886b00d4277a32a7b" として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2740-127">For example, the thumbprint "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b" should be specified as "a909502dd82ae41433e6f83886b00d4277a32a7b" in code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2740-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2740-128">See also</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>
- [<span data-ttu-id="d2740-129">方法: SSL 証明書でポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="d2740-129">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="d2740-130">方法: MMC スナップインで証明書の表示</span><span class="sxs-lookup"><span data-stu-id="d2740-130">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="d2740-131">方法: 開発中に使用するための一時的な証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="d2740-131">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
