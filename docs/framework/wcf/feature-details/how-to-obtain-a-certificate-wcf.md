---
title: '方法: (WCF) 証明書を取得します。'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 21e9e0609ed63c4398f2df7ba718f8af17464b0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683633"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="875bf-102">方法: (WCF) 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="875bf-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="875bf-103">Windows Communication Foundation (WCF) のいずれかを使用するには、その機能を使用して、X.509 証明書の最初に証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="875bf-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="875bf-104">X.509 証明書を取得するには</span><span class="sxs-lookup"><span data-stu-id="875bf-104">To obtain an X.509 certificate</span></span>  
  
1. <span data-ttu-id="875bf-105">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="875bf-105">Choose one of the following:</span></span>  
  
    - <span data-ttu-id="875bf-106">VeriSign, Inc. などの証明機関から証明書を購入します。</span><span class="sxs-lookup"><span data-stu-id="875bf-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    - <span data-ttu-id="875bf-107">独自の証明書サービスを設定し、証明機関に証明書への署名を依頼します。</span><span class="sxs-lookup"><span data-stu-id="875bf-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]<span data-ttu-id="875bf-108">、Windows 2000 Server、Windows 2000 Server Datacenter、および Windows 2000 Datacenter Server にはすべて、公開キー基盤 (PKI) をサポートする証明書サービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="875bf-108">, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="875bf-109">Windows Server 2008 で使用して、 [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483)証明機関を管理します。</span><span class="sxs-lookup"><span data-stu-id="875bf-109">In Windows Server 2008, use the [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483) role to manage a certification authority.</span></span>  
  
    - <span data-ttu-id="875bf-110">独自の証明書サービスを設定し、証明書には署名しません。</span><span class="sxs-lookup"><span data-stu-id="875bf-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="875bf-111">どの方法を使用する場合でも、X.509 証明書を含む SOAP 要求の受信者は、その X.509 証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="875bf-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="875bf-112">つまり、証明書チェーン内の X.509 証明書または発行者は、信頼されたユーザーの証明書ストア内に存在し、また X.509 証明書は信頼されない証明書ストア内には存在しないということを意味します。</span><span class="sxs-lookup"><span data-stu-id="875bf-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875bf-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="875bf-113">See also</span></span>

- [<span data-ttu-id="875bf-114">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="875bf-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="875bf-115">方法: 開発中に使用するための一時的な証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="875bf-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
