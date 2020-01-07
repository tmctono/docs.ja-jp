---
title: '方法 : X.509 証明書を WCF からアクセス可能にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 7f24966f06730e62ea7a8967c3930f05ca78f50e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347080"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="d8f9b-102">方法 : X.509 証明書を WCF からアクセス可能にする</span><span class="sxs-lookup"><span data-stu-id="d8f9b-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="d8f9b-103">Windows Communication Foundation (WCF) から x.509 証明書にアクセスできるようにするには、アプリケーションコードで証明書ストアの名前と場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="d8f9b-104">特定の状況では、X.509 証明書に関連付けられた秘密キーを格納しているファイルにプロセス ID がアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="d8f9b-105">証明書ストアの x.509 証明書に関連付けられている秘密キーを取得するには、WCF にアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="d8f9b-106">既定では、所有者と System アカウントだけが証明書の秘密キーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="d8f9b-107">X.509 証明書を WCF からアクセス可能にするには</span><span class="sxs-lookup"><span data-stu-id="d8f9b-107">To make X.509 certificates accessible to WCF</span></span>  
  
1. <span data-ttu-id="d8f9b-108">WCF が実行されているアカウントに、x.509 証明書に関連付けられている秘密キーを含むファイルへの読み取りアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1. <span data-ttu-id="d8f9b-109">WCF が x.509 証明書の秘密キーへの読み取りアクセスを必要とするかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="d8f9b-110">次の表は、X.509 証明書を使用する際に秘密キーを使用できる必要があるかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="d8f9b-111">X.509 証明書の使用法</span><span class="sxs-lookup"><span data-stu-id="d8f9b-111">X.509 certificate use</span></span>|<span data-ttu-id="d8f9b-112">秘密キー</span><span class="sxs-lookup"><span data-stu-id="d8f9b-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="d8f9b-113">送信 SOAP メッセージにデジタル署名する。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="d8f9b-114">○</span><span class="sxs-lookup"><span data-stu-id="d8f9b-114">Yes</span></span>|  
        |<span data-ttu-id="d8f9b-115">受信 SOAP メッセージの署名を検証する。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="d8f9b-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8f9b-116">No</span></span>|  
        |<span data-ttu-id="d8f9b-117">送信 SOAP メッセージを暗号化する。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="d8f9b-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8f9b-118">No</span></span>|  
        |<span data-ttu-id="d8f9b-119">受信 SOAP メッセージを復号化する。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="d8f9b-120">○</span><span class="sxs-lookup"><span data-stu-id="d8f9b-120">Yes</span></span>|  
  
    2. <span data-ttu-id="d8f9b-121">証明書が格納されている証明書ストアの場所と名前を決定します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="d8f9b-122">証明書が格納されている証明書ストアは、アプリケーション コードまたは構成で指定します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="d8f9b-123">たとえば、次の例では、証明書が `CurrentUser` という名前の `My` 証明書ストア内に存在することを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. <span data-ttu-id="d8f9b-124">[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)ツールを使用して、証明書の秘密キーがコンピューター上にある場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="d8f9b-125">[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)ツールには、証明書ストアの名前、証明書ストアの場所、および証明書を一意に識別するものが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="d8f9b-126">このツールは、証明書のサブジェクト名または拇印を一意の識別子として受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="d8f9b-127">証明書の拇印を確認する方法の詳細については、「[方法: 証明書のサムプリントを取得](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="d8f9b-128">次のコード例では、 [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)ツールを使用して、拇印が `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`の `CurrentUser` の `My` ストアにある証明書の秘密キーの場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. <span data-ttu-id="d8f9b-129">WCF が実行されているアカウントを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="d8f9b-130">次の表は、特定のシナリオで WCF が実行されているアカウントの詳細を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="d8f9b-131">通信の種類</span><span class="sxs-lookup"><span data-stu-id="d8f9b-131">Scenario</span></span>|<span data-ttu-id="d8f9b-132">プロセス ID</span><span class="sxs-lookup"><span data-stu-id="d8f9b-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="d8f9b-133">クライアント (コンソールまたは WinForms アプリケーション)</span><span class="sxs-lookup"><span data-stu-id="d8f9b-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="d8f9b-134">現在ログインしているユーザー</span><span class="sxs-lookup"><span data-stu-id="d8f9b-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="d8f9b-135">自己ホスト型のサービス</span><span class="sxs-lookup"><span data-stu-id="d8f9b-135">Service that is self-hosted.</span></span>|<span data-ttu-id="d8f9b-136">現在ログインしているユーザー</span><span class="sxs-lookup"><span data-stu-id="d8f9b-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="d8f9b-137">IIS 6.0 (Windows Server 2003) または IIS 7.0 (Windows Vista) でホストされるサービス。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-137">Service that is hosted in IIS 6.0 (Windows Server 2003) or IIS 7.0 (Windows Vista).</span></span>|<span data-ttu-id="d8f9b-138">NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="d8f9b-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="d8f9b-139">IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]) でホストされているサービス</span><span class="sxs-lookup"><span data-stu-id="d8f9b-139">Service that is hosted in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span></span>|<span data-ttu-id="d8f9b-140">Machine.config ファイル内の `<processModel>` 要素によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="d8f9b-141">既定のアカウントは ASPNET です。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-141">The default account is ASPNET.</span></span>|  
  
    5. <span data-ttu-id="d8f9b-142">Icacls などのツールを使用して、WCF を実行しているアカウントに、秘密キーを含むファイルへの読み取りアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as icacls.exe.</span></span>  
  
         <span data-ttu-id="d8f9b-143">次のコード例では、指定されたファイルの随意アクセス制御リスト (DACL) を編集して、ネットワークサービスアカウントにファイルへの読み取り (: R) アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="d8f9b-143">The following code example edits the discretionary access control list (DACL) for the specified file to grant the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```console 
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="d8f9b-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8f9b-144">See also</span></span>

- [<span data-ttu-id="d8f9b-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="d8f9b-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [<span data-ttu-id="d8f9b-146">方法 : 証明書のサムプリントを取得する</span><span class="sxs-lookup"><span data-stu-id="d8f9b-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [<span data-ttu-id="d8f9b-147">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="d8f9b-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
