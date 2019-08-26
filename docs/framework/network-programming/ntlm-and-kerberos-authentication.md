---
title: NTLM 認証および Kerberos 認証
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], NTLM
- authentication [.NET Framework], Kerberos
- user authentication, Kerberos
- user authentication, NTLM
- Kerberos authentication
- receiving data, authentication
- NTLM authentication
- Internet, authentication
- client authentication, Kerberos
- sending data, authentication
- network resources, authentication
- classes [.NET Framework], authentication
- client authentication, NTLM
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
ms.openlocfilehash: b05cd88fcb492ab27e1d311045b72208167508f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963925"
---
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="86588-102">NTLM 認証および Kerberos 認証</span><span class="sxs-lookup"><span data-stu-id="86588-102">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="86588-103">既定の NTLM 認証と Kerberos 認証は、呼び出し元のアプリケーションに関連付けられている Microsoft Windows NT ユーザー資格情報を使用して、サーバーで認証を試みます。</span><span class="sxs-lookup"><span data-stu-id="86588-103">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="86588-104">既定以外の NTLM 認証を使用する場合、アプリケーションは認証の種類を NTLM に設定し、次の例に示すように <xref:System.Net.NetworkCredential> オブジェクトを使用して、ユーザー名、パスワード、およびドメインをホストに渡します。</span><span class="sxs-lookup"><span data-stu-id="86588-104">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =   
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 <span data-ttu-id="86588-105">アプリケーション ユーザーの資格情報を使用してインターネット サービスに接続する必要があるアプリケーションは、次の例に示すように、ユーザーの既定の資格情報を使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="86588-105">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 <span data-ttu-id="86588-106">ネゴシエート認証モジュールは、リモート サーバーが NTLM 認証を使用しているか Kerberos 認証を使用しているかを確認し、適切な応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="86588-106">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86588-107">NTLM 認証は、プロキシ サーバー経由では機能しません。</span><span class="sxs-lookup"><span data-stu-id="86588-107">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86588-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="86588-108">See also</span></span>

- [<span data-ttu-id="86588-109">基本認証とダイジェスト認証</span><span class="sxs-lookup"><span data-stu-id="86588-109">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)
- [<span data-ttu-id="86588-110">インターネット認証</span><span class="sxs-lookup"><span data-stu-id="86588-110">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
