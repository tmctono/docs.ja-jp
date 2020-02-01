---
title: '方法 : SSL 証明書を使用してポートを構成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 412aa2bb2a56fbe654b0d9ce5f4b9b5176fc5549
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921299"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="30b94-102">方法 : SSL 証明書を使用してポートを構成する</span><span class="sxs-lookup"><span data-stu-id="30b94-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="30b94-103">トランスポートセキュリティを使用する <xref:System.ServiceModel.WSHttpBinding> クラスを使用して、自己ホスト型 Windows Communication Foundation (WCF) サービスを作成する場合は、x.509 証明書を使用してポートを構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="30b94-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="30b94-104">自己ホスト型サービスを作成するのでなければ、インターネット インフォメーション サービス (IIS) でサービスをホストできます。</span><span class="sxs-lookup"><span data-stu-id="30b94-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="30b94-105">詳細については、「 [HTTP トランスポートセキュリティ](../../../../docs/framework/wcf/feature-details/http-transport-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b94-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="30b94-106">ポートを構成する場合に使用するツールは、コンピューターで実行されているオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="30b94-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="30b94-107">Windows Server 2003 または Windows XP を実行している場合は、Httpcfg.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="30b94-107">If you are running Windows Server 2003 or Windows XP, use the HttpCfg.exe tool.</span></span> <span data-ttu-id="30b94-108">Windows Server 2003 では、このツールはインストールされています。</span><span class="sxs-lookup"><span data-stu-id="30b94-108">With Windows Server 2003 this tool is installed.</span></span> <span data-ttu-id="30b94-109">Windows XP では、 [WINDOWS Xp Service Pack 2 サポートツール](https://go.microsoft.com/fwlink/?LinkId=88606)でツールをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="30b94-109">With Windows XP, you can download the tool at [Windows XP Service Pack 2 Support Tools](https://go.microsoft.com/fwlink/?LinkId=88606).</span></span> <span data-ttu-id="30b94-110">詳細については、「 [httpcfg.exe の概要](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b94-110">For more information, see [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span></span> <span data-ttu-id="30b94-111">[Windows サポートツールのドキュメント](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10))では、httpcfg.exe ツールの構文について説明しています。</span><span class="sxs-lookup"><span data-stu-id="30b94-111">The [Windows Support Tools documentation](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="30b94-112">Windows Vista を実行している場合は、既にインストールされている Netsh.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="30b94-112">If you are running Windows Vista, use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="30b94-113">このトピックでは、次のようなさまざまな手順を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="30b94-113">This topic describes how to accomplish several procedures:</span></span>  
  
- <span data-ttu-id="30b94-114">コンピューターの現在のポート構成を確認する。</span><span class="sxs-lookup"><span data-stu-id="30b94-114">Determining a computer's current port configuration.</span></span>  
  
- <span data-ttu-id="30b94-115">証明書の拇印を取得する (次の 2 つの手順に必要)。</span><span class="sxs-lookup"><span data-stu-id="30b94-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
- <span data-ttu-id="30b94-116">SSL 証明書をポート構成にバインドする。</span><span class="sxs-lookup"><span data-stu-id="30b94-116">Binding an SSL certificate to a port configuration.</span></span>  
  
- <span data-ttu-id="30b94-117">SSL 証明書をポート構成にバインドし、クライアント証明書をサポートする。</span><span class="sxs-lookup"><span data-stu-id="30b94-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
- <span data-ttu-id="30b94-118">ポート番号から SSL 証明書を削除する。</span><span class="sxs-lookup"><span data-stu-id="30b94-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="30b94-119">コンピューターに格納されている証明書を変更するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="30b94-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="30b94-120">ポートの構成を確認するには</span><span class="sxs-lookup"><span data-stu-id="30b94-120">To determine how ports are configured</span></span>  
  
1. <span data-ttu-id="30b94-121">Windows Server 2003 または Windows XP では、Httpcfg.exe ツールを使用して、次の例に示すように、**クエリ**と**ssl**スイッチを使用して現在のポート構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="30b94-121">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="30b94-122">Windows Vista では、次の例に示すように、Netsh.exe ツールを使用して現在のポート構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="30b94-122">In Windows Vista, use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="30b94-123">証明書の拇印を取得するには</span><span class="sxs-lookup"><span data-stu-id="30b94-123">To get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="30b94-124">証明書 MMC スナップインを使用して、クライアント認証を目的として含む X.509 証明書を検索します。</span><span class="sxs-lookup"><span data-stu-id="30b94-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="30b94-125">詳細については、「[方法: MMC スナップインを使用して証明書を参照する](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b94-125">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="30b94-126">証明書の拇印にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="30b94-126">Access the certificate's thumbprint.</span></span> <span data-ttu-id="30b94-127">詳細については、「[方法: 証明書のサムプリントを取得する](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b94-127">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="30b94-128">証明書のサムプリントを、メモ帳などのテキスト エディターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="30b94-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="30b94-129">16 進文字の間にある空白をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="30b94-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="30b94-130">たとえばエディターの "すべて置換" 機能を使用して、空白を空文字列に置き換えるとよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="30b94-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="30b94-131">SSL 証明書をポート番号にバインドするには</span><span class="sxs-lookup"><span data-stu-id="30b94-131">To bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="30b94-132">Windows Server 2003 または Windows XP では、Secure Sockets Layer (SSL) ストアの "設定" モードで Httpcfg.exe ツールを使用して、証明書をポート番号にバインドします。</span><span class="sxs-lookup"><span data-stu-id="30b94-132">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="30b94-133">このツールは、次のように、拇印を使用して証明書を識別します。</span><span class="sxs-lookup"><span data-stu-id="30b94-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="30b94-134">**-I**スイッチの構文は `IP`:`port` で、コンピューターのポート8012に証明書を設定するようにツールに指示します。</span><span class="sxs-lookup"><span data-stu-id="30b94-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="30b94-135">"0.0.0.0" の部分は、必要に応じて、コンピューターの実際の IP アドレスに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="30b94-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="30b94-136">**-H**スイッチは、証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="30b94-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="30b94-137">Windows Vista では、次の例に示すように、Netsh.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="30b94-137">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    - <span data-ttu-id="30b94-138">**Certhash**パラメーターは、証明書の拇印を指定します。</span><span class="sxs-lookup"><span data-stu-id="30b94-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="30b94-139">**Ipport**パラメーターは、IP アドレスとポートを指定し、httpcfg.exe ツールの **-i**スイッチと同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="30b94-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="30b94-140">**Appid**パラメーターは、所有しているアプリケーションを識別するために使用できる GUID です。</span><span class="sxs-lookup"><span data-stu-id="30b94-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="30b94-141">SSL 証明書をポート番号にバインドし、クライアント証明書をサポートするには</span><span class="sxs-lookup"><span data-stu-id="30b94-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="30b94-142">Windows Server 2003 または Windows XP で、トランスポート層で x.509 証明書を使用して認証を行うクライアントをサポートするには、前の手順に従いますが、次の例に示すように、Httpcfg.exe に追加のコマンドラインパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="30b94-142">In Windows Server 2003 or Windows XP, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="30b94-143">**-F**スイッチには `n` の構文があります。 n は 1 ~ 7 の数値です。</span><span class="sxs-lookup"><span data-stu-id="30b94-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="30b94-144">前の例のように 2 を指定すると、クライアントはトランスポート層で認証することになります。</span><span class="sxs-lookup"><span data-stu-id="30b94-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="30b94-145">値として 3 を指定すると、クライアント証明書が有効になり、それらの証明書が Windows アカウントに対応付けられます。</span><span class="sxs-lookup"><span data-stu-id="30b94-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="30b94-146">他の値については、HttpCfg.exe のヘルプ機能を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b94-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="30b94-147">Windows Vista で、トランスポート層で x.509 証明書を使用して認証を行うクライアントをサポートするには、次の例に示すように、上記の手順に従いますが、追加のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="30b94-147">In Windows Vista, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="30b94-148">ポート番号から SSL 証明書を削除するには</span><span class="sxs-lookup"><span data-stu-id="30b94-148">To delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="30b94-149">HttpCfg.exe または Netsh.exe ツールを使用して、コンピューター上のすべてのバインディングのポートと拇印を確認します。</span><span class="sxs-lookup"><span data-stu-id="30b94-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="30b94-150">情報をディスクに出力するには、次の例に示すように、リダイレクト文字 ">" を使用します。</span><span class="sxs-lookup"><span data-stu-id="30b94-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="30b94-151">Windows Server 2003 または Windows XP では、Httpcfg.exe ツールと**delete**および**ssl**キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="30b94-151">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="30b94-152">**-I**スイッチを使用して `IP`を指定します。`port` 番号、 **-h**スイッチを使用してサムプリントを指定します。</span><span class="sxs-lookup"><span data-stu-id="30b94-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="30b94-153">Windows Vista では、次の例に示すように、Netsh.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="30b94-153">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="30b94-154">使用例</span><span class="sxs-lookup"><span data-stu-id="30b94-154">Example</span></span>  
 <span data-ttu-id="30b94-155">次のコードは、トランスポート セキュリティを設定した <xref:System.ServiceModel.WSHttpBinding> クラスを使用して、自己ホスト型サービスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="30b94-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="30b94-156">アプリケーションを作成する際、アドレス中にポート番号を指定してください。</span><span class="sxs-lookup"><span data-stu-id="30b94-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="30b94-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="30b94-157">See also</span></span>

- [<span data-ttu-id="30b94-158">HTTP トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="30b94-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
