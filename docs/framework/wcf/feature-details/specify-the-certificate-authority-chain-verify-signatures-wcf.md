---
title: '方法: 署名 (WCF) を確認するために使用する証明機関証明書チェーンを指定します。'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 43296fad9519a08db5facdd220492ac70dffeca2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747642"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a><span data-ttu-id="febc9-102">方法: 署名 (WCF) を確認するために使用する証明機関証明書チェーンを指定します。</span><span class="sxs-lookup"><span data-stu-id="febc9-102">How to: Specify the Certificate Authority Certificate Chain Used to Verify Signatures (WCF)</span></span>
<span data-ttu-id="febc9-103">Windows Communication Foundation (WCF) では、X.509 証明書を使用して署名された SOAP メッセージを受信したときに既定ではことを確認、X.509 証明書が信頼された証明機関によって発行されたことです。</span><span class="sxs-lookup"><span data-stu-id="febc9-103">When Windows Communication Foundation (WCF) receives a SOAP message signed using an X.509 certificate, by default it verifies that the X.509 certificate was issued by a trusted certification authority.</span></span> <span data-ttu-id="febc9-104">これは、証明書ストアを検索し、その証明機関の証明書が信頼された証明書として指定されているかどうかを確認することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="febc9-104">This is done by looking in a certificate store and determining if the certificate for that certification authority has been designated as trusted.</span></span> <span data-ttu-id="febc9-105">WCF この判断を行うためには、適切な証明書ストアに証明機関の証明書チェーンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="febc9-105">In order for WCF to make this determination, the certification authority certificate chain must be installed in the correct certificate store.</span></span>  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a><span data-ttu-id="febc9-106">証明機関証明書チェーンをインストールするには</span><span class="sxs-lookup"><span data-stu-id="febc9-106">To install a certification authority certificate chain</span></span>  
  
- <span data-ttu-id="febc9-107">各 SOAP メッセージの受信者によって信頼される証明機関から X.509 証明書を取得する、WCF が構成されている証明書ストアに証明機関の証明書チェーンをインストール、発行された X.509 証明書。</span><span class="sxs-lookup"><span data-stu-id="febc9-107">For each certification authority that a SOAP message recipient intends to trust X.509 certificates issued from, install the certification authority certificate chain into the certificate store that WCF is configured to retrieve X.509 certificates from.</span></span>  
  
     <span data-ttu-id="febc9-108">たとえば、SOAP メッセージの受信者は、マイクロソフトによって発行された X.509 証明書を信頼するが場合の Microsoft 証明機関の証明書チェーンを WCF が X.509 証明書の検索に設定されている証明書ストアにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="febc9-108">For instance, if a SOAP message recipient intends to trust X.509 certificates issued by Microsoft, the certification authority certificate chain for Microsoft must be installed in the certificate store that WCF is set up to look for X.509 certificates from.</span></span> <span data-ttu-id="febc9-109">コードまたは構成では、WCF が X.509 証明書を検索する場合に、証明書ストアを指定できます。</span><span class="sxs-lookup"><span data-stu-id="febc9-109">The certificate store in which WCF looks for X.509 certificates can be specified in code or configuration.</span></span> <span data-ttu-id="febc9-110">これを指定してコードを使用してなど、<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>メソッドまたは構成など、いくつかの点で、 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="febc9-110">For example, this can be specified in code using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method or in configuration a few ways, including the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .</span></span>  
  
     <span data-ttu-id="febc9-111">Windows には、信頼された証明機関の既定の証明書チェーンのセットが用意されているため、一部の CA については証明書チェーンをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="febc9-111">Because Windows ships with a set of default certificate chains for trusted certificate authorities, it may not be necessary to install the certificate chain for all certificate authorities.</span></span>  
  
    1. <span data-ttu-id="febc9-112">証明機関証明書チェーンをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="febc9-112">Export the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="febc9-113">正確なエクスポート方法は、証明機関によって異なります。</span><span class="sxs-lookup"><span data-stu-id="febc9-113">Exactly how this is done depends on the certification authority.</span></span> <span data-ttu-id="febc9-114">証明機関で Microsoft 証明書サービスが実行されている場合は、選択**CA 証明書、証明書チェーン、または CRL のダウンロード**を選び、**ダウンロードの CA 証明書**します。</span><span class="sxs-lookup"><span data-stu-id="febc9-114">If the certification authority is running Microsoft Certificate Services, select **Download a CA certificate, certificate chain, or CRL**, and then choose **Download CA certificate**.</span></span>  
  
    2. <span data-ttu-id="febc9-115">証明機関証明書チェーンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="febc9-115">Import the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="febc9-116">Microsoft 管理コンソール (MMC: Microsoft Management Console) で、証明書スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="febc9-116">In the Microsoft Management Console (MMC), open the Certificates snap-in.</span></span> <span data-ttu-id="febc9-117">選択から X.509 証明書を取得する証明書ストアにその WCF が構成されている、**信頼されたルート** **証明機関**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="febc9-117">For the certificate store that WCF is configured to retrieve X.509 certificates from, select the **Trusted Root** **Certification Authorities** folder.</span></span> <span data-ttu-id="febc9-118">下、**信頼されたルート証明機関**フォルダーを右クリックし、**証明書**フォルダーを指す**すべてのタスク**、順にクリックします**インポート**.</span><span class="sxs-lookup"><span data-stu-id="febc9-118">Under the **Trusted Root Certification Authorities** folder, right-click the **Certificates** folder, point to **All Tasks**, and then click **Import**.</span></span> <span data-ttu-id="febc9-119">手順 a. でエクスポートしたファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="febc9-119">Provide the file exported in step a.</span></span>  
  
         <span data-ttu-id="febc9-120">詳細については、MMC で証明書スナップインを使用して、次を参照してください。[方法。MMC スナップインで証明書を表示](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)します。</span><span class="sxs-lookup"><span data-stu-id="febc9-120">For more information about using the Certificates snap-in with MMC, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febc9-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="febc9-121">See also</span></span>

- [<span data-ttu-id="febc9-122">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="febc9-122">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
