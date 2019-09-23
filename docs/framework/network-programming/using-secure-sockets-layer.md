---
title: Secure Sockets Layerの使用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Networking
- SSL
- Secure Sockets Layer
- requesting data from Internet, Secure Sockets Layer
- sending data, Secure Sockets Layer
- Network Resources
- data requests, Secure Sockets Layer
- receiving data, Secure Sockets Layer
- Internet, Secure Sockets Layer
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
ms.openlocfilehash: ef2abc7574aea1b4f77ff93545ad84678c66ce48
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046904"
---
# <a name="using-secure-sockets-layer"></a><span data-ttu-id="98f30-102">Secure Sockets Layerの使用</span><span class="sxs-lookup"><span data-stu-id="98f30-102">Using Secure Sockets Layer</span></span>
<span data-ttu-id="98f30-103"><xref:System.Net> クラスは、Secure Sockets Layer (SSL) を使用して、複数のネットワーク プロトコルの接続を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="98f30-103">The <xref:System.Net> classes use the Secure Sockets Layer (SSL) to encrypt the connection for several network protocols.</span></span>  
  
 <span data-ttu-id="98f30-104">HTTP 接続の場合、<xref:System.Net.WebRequest> クラスと <xref:System.Net.WebResponse> クラスは SSL を使用して、SSL をサポートする Web ホストと通信します。</span><span class="sxs-lookup"><span data-stu-id="98f30-104">For http connections, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes use SSL to communicate with web hosts that support SSL.</span></span> <span data-ttu-id="98f30-105">SSL の使用は、指定された URI に基づいて <xref:System.Net.WebRequest> クラスで決定されます。</span><span class="sxs-lookup"><span data-stu-id="98f30-105">The decision to use SSL is made by the <xref:System.Net.WebRequest> class, based on the URI it is given.</span></span> <span data-ttu-id="98f30-106">URI が "https:" で始まる場合は SSL が使用されます。URI が "http:" で始まる場合は、暗号化されていない接続が使用されます。</span><span class="sxs-lookup"><span data-stu-id="98f30-106">If the URI begins with "https:", SSL is used; if the URI begins with "http:", an unencrypted connection is used.</span></span>  
  
 <span data-ttu-id="98f30-107">ファイル転送プロトコル (FTP) で SSL を使用するには、<xref:System.Net.FtpWebRequest.EnableSsl> プロパティを true に設定してから <xref:System.Net.FtpWebRequest.GetResponse> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="98f30-107">To use SSL with File Transfer Protocol (FTP), set the <xref:System.Net.FtpWebRequest.EnableSsl> property to true prior to calling <xref:System.Net.FtpWebRequest.GetResponse>.</span></span> <span data-ttu-id="98f30-108">同様に、簡易メール転送プロトコル (SMTP) で SSL を使用するには、<xref:System.Net.Mail.SmtpClient.EnableSsl> プロパティを true に設定してからメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="98f30-108">Similarly, to use SSL with Simple Mail Transport Protocol (SMTP), set the <xref:System.Net.Mail.SmtpClient.EnableSsl> property to true prior to sending the email.</span></span>  
  
 <span data-ttu-id="98f30-109"><xref:System.Net.Security.SslStream> クラスは、SSL のストリームベースの抽象化を提供します。また、SSL ハンドシェイクを構成する方法が多く用意されています。</span><span class="sxs-lookup"><span data-stu-id="98f30-109">The <xref:System.Net.Security.SslStream> class provides a stream-based abstraction for SSL, and offers many ways to configure the SSL handshake.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98f30-110">例</span><span class="sxs-lookup"><span data-stu-id="98f30-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="98f30-111">コード</span><span class="sxs-lookup"><span data-stu-id="98f30-111">Code</span></span>  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="98f30-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="98f30-112">Compiling the Code</span></span>  
 <span data-ttu-id="98f30-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="98f30-113">This example requires:</span></span>  
  
- <span data-ttu-id="98f30-114">**System.Net** 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="98f30-114">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f30-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="98f30-115">See also</span></span>

- [<span data-ttu-id="98f30-116">ネットワーク プログラミングにおけるセキュリティ</span><span class="sxs-lookup"><span data-stu-id="98f30-116">Security in Network Programming</span></span>](security-in-network-programming.md)
- [<span data-ttu-id="98f30-117">.NET Framework のネットワーク プログラミング</span><span class="sxs-lookup"><span data-stu-id="98f30-117">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="98f30-118">証明書の選択と検証</span><span class="sxs-lookup"><span data-stu-id="98f30-118">Certificate Selection and Validation</span></span>](certificate-selection-and-validation.md)
