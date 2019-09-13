---
title: '方法: SSL 証明書を使用してポートを構成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 6e21311802b0a3ce4e415b14686b101d31f18035
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70893312"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="7bd0b-102">方法: SSL 証明書を使用してポートを構成する</span><span class="sxs-lookup"><span data-stu-id="7bd0b-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="7bd0b-103">トランスポートセキュリティを使用するクラスを使用し<xref:System.ServiceModel.WSHttpBinding>て自己ホスト型 Windows Communication Foundation (WCF) サービスを作成する場合は、x.509 証明書を使用してポートを構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="7bd0b-104">自己ホスト型サービスを作成するのでなければ、インターネット インフォメーション サービス (IIS) でサービスをホストできます。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="7bd0b-105">詳細については、「 [HTTP トランスポートセキュリティ](../../../../docs/framework/wcf/feature-details/http-transport-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="7bd0b-106">ポートを構成する場合に使用するツールは、コンピューターで実行されているオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="7bd0b-107">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] または [!INCLUDE[wxp](../../../../includes/wxp-md.md)] を実行している場合は、HttpCfg.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-107">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool.</span></span> <span data-ttu-id="7bd0b-108">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] では、このツールは自動的にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-108">With [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] this tool is installed.</span></span> <span data-ttu-id="7bd0b-109">では、Windows [XP Service Pack 2 サポートツール](https://go.microsoft.com/fwlink/?LinkId=88606)からツールをダウンロードできます。 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bd0b-109">With [!INCLUDE[wxp](../../../../includes/wxp-md.md)], you can download the tool at [Windows XP Service Pack 2 Support Tools](https://go.microsoft.com/fwlink/?LinkId=88606).</span></span> <span data-ttu-id="7bd0b-110">詳細については、「 [httpcfg.exe の概要](https://go.microsoft.com/fwlink/?LinkId=88605)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-110">For more information, see [Httpcfg Overview](https://go.microsoft.com/fwlink/?LinkId=88605).</span></span> <span data-ttu-id="7bd0b-111">[Windows サポートツールのドキュメント](https://go.microsoft.com/fwlink/?LinkId=94840)では、httpcfg.exe ツールの構文について説明しています。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-111">The [Windows Support Tools documentation](https://go.microsoft.com/fwlink/?LinkId=94840) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="7bd0b-112">[!INCLUDE[wv](../../../../includes/wv-md.md)] を実行している場合は、Netsh.exe ツールを使用します。これは既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-112">If you are running [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="7bd0b-113">このトピックでは、次のようなさまざまな手順を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-113">This topic describes how to accomplish several procedures:</span></span>  
  
- <span data-ttu-id="7bd0b-114">コンピューターの現在のポート構成を確認する。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-114">Determining a computer's current port configuration.</span></span>  
  
- <span data-ttu-id="7bd0b-115">証明書の拇印を取得する (次の 2 つの手順に必要)。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
- <span data-ttu-id="7bd0b-116">SSL 証明書をポート構成にバインドする。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-116">Binding an SSL certificate to a port configuration.</span></span>  
  
- <span data-ttu-id="7bd0b-117">SSL 証明書をポート構成にバインドし、クライアント証明書をサポートする。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
- <span data-ttu-id="7bd0b-118">ポート番号から SSL 証明書を削除する。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="7bd0b-119">コンピューターに格納されている証明書を変更するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="7bd0b-120">ポートの構成を確認するには</span><span class="sxs-lookup"><span data-stu-id="7bd0b-120">To determine how ports are configured</span></span>  
  
1. <span data-ttu-id="7bd0b-121">また[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]は[!INCLUDE[wxp](../../../../includes/wxp-md.md)]では、次の例に示すように、httpcfg.exe ツールを使用して、**クエリ**と**ssl**スイッチを使用して現在のポート構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="7bd0b-122">[!INCLUDE[wv](../../../../includes/wv-md.md)] で現在のポート構成を表示するには、Netsh.exe ツールを使用します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-122">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="7bd0b-123">証明書の拇印を取得するには</span><span class="sxs-lookup"><span data-stu-id="7bd0b-123">To get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="7bd0b-124">証明書 MMC スナップインを使用して、クライアント認証を目的として含む X.509 証明書を検索します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="7bd0b-125">詳細については、「[方法 :MMC スナップ](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)インを使用して証明書を表示します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-125">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="7bd0b-126">証明書の拇印にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-126">Access the certificate's thumbprint.</span></span> <span data-ttu-id="7bd0b-127">詳細については、「[方法 :証明書](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)の拇印を取得します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-127">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="7bd0b-128">証明書のサムプリントを、メモ帳などのテキスト エディターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="7bd0b-129">16 進文字の間にある空白をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="7bd0b-130">たとえばエディターの "すべて置換" 機能を使用して、空白を空文字列に置き換えるとよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="7bd0b-131">SSL 証明書をポート番号にバインドするには</span><span class="sxs-lookup"><span data-stu-id="7bd0b-131">To bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="7bd0b-132">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] または [!INCLUDE[wxp](../../../../includes/wxp-md.md)] で証明書をポート番号にバインドするには、HttpCfg.exe ツールを SSL (Secure Sockets Layer) ストアに対して "set" モードで使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="7bd0b-133">このツールは、次のように、拇印を使用して証明書を識別します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="7bd0b-134">**-I**スイッチの構文`IP`はです`port` 。は、コンピューターのポート8012に証明書を設定するようにツールに指示します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="7bd0b-135">"0.0.0.0" の部分は、必要に応じて、コンピューターの実際の IP アドレスに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="7bd0b-136">**-H**スイッチは、証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="7bd0b-137">[!INCLUDE[wv](../../../../includes/wv-md.md)] では、Netsh.exe ツールを使用します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-137">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    - <span data-ttu-id="7bd0b-138">**Certhash**パラメーターは、証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="7bd0b-139">**Ipport**パラメーターは、IP アドレスとポートを指定し、httpcfg.exe ツールの **-i**スイッチと同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="7bd0b-140">**Appid**パラメーターは、所有しているアプリケーションを識別するために使用できる GUID です。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="7bd0b-141">SSL 証明書をポート番号にバインドし、クライアント証明書をサポートするには</span><span class="sxs-lookup"><span data-stu-id="7bd0b-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="7bd0b-142">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] または [!INCLUDE[wxp](../../../../includes/wxp-md.md)] では、トランスポート層で X.509 証明書を使用して認証するクライアントをサポートするには、前と同じ手順を実行しますが、次のように HttpCfg.exe に追加のコマンド ライン パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="7bd0b-143">**-F**スイッチには、の構文`n`があります。 n は 1 ~ 7 の数値です。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="7bd0b-144">前の例のように 2 を指定すると、クライアントはトランスポート層で認証することになります。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="7bd0b-145">値として 3 を指定すると、クライアント証明書が有効になり、それらの証明書が Windows アカウントに対応付けられます。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="7bd0b-146">他の値については、HttpCfg.exe のヘルプ機能を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="7bd0b-147">[!INCLUDE[wv](../../../../includes/wv-md.md)] では、トランスポート層で X.509 証明書を使用して認証するクライアントをサポートするには、前と同じ手順を実行しますが、次のように追加のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-147">In [!INCLUDE[wv](../../../../includes/wv-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="7bd0b-148">ポート番号から SSL 証明書を削除するには</span><span class="sxs-lookup"><span data-stu-id="7bd0b-148">To delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="7bd0b-149">HttpCfg.exe または Netsh.exe ツールを使用して、コンピューター上のすべてのバインディングのポートと拇印を確認します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="7bd0b-150">情報をディスクに出力するには、次の例のようにリダイレクト文字 ">" を使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="7bd0b-151">また[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]は[!INCLUDE[wxp](../../../../includes/wxp-md.md)]では、httpcfg.exe ツールと**delete**および**ssl**キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="7bd0b-152">**-I**スイッチを使用して、 `IP`:`port` number を指定し、 **-h**スイッチを使用してサムプリントを指定します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="7bd0b-153">[!INCLUDE[wv](../../../../includes/wv-md.md)] では、Netsh.exe ツールを使用します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-153">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="7bd0b-154">例</span><span class="sxs-lookup"><span data-stu-id="7bd0b-154">Example</span></span>  
 <span data-ttu-id="7bd0b-155">次のコードは、トランスポート セキュリティを設定した <xref:System.ServiceModel.WSHttpBinding> クラスを使用して、自己ホスト型サービスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="7bd0b-156">アプリケーションを作成する際、アドレス中にポート番号を指定してください。</span><span class="sxs-lookup"><span data-stu-id="7bd0b-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7bd0b-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bd0b-157">See also</span></span>

- [<span data-ttu-id="7bd0b-158">HTTP トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="7bd0b-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
