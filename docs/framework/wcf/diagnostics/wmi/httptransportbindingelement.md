---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 5e23342d57621554aaec67c5c568bb75202a9454
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977042"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="67c1d-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="67c1d-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="67c1d-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="67c1d-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c1d-104">構文</span><span class="sxs-lookup"><span data-stu-id="67c1d-104">Syntax</span></span>  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="67c1d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="67c1d-105">Methods</span></span>  
 <span data-ttu-id="67c1d-106">HttpTransportBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="67c1d-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="67c1d-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="67c1d-107">Properties</span></span>  
 <span data-ttu-id="67c1d-108">HttpTransportBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="67c1d-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="67c1d-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="67c1d-109">AllowCookies</span></span>  
 <span data-ttu-id="67c1d-110">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="67c1d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="67c1d-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-112">クライアントがクッキーを受け入れて、それらを今後の要求に反映させるかどうかを指定する値です。</span><span class="sxs-lookup"><span data-stu-id="67c1d-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="67c1d-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="67c1d-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="67c1d-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="67c1d-114">Data type: string</span></span>  
  
 <span data-ttu-id="67c1d-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-116">HTTP リスナーにより処理されているクライアント要求の認証に使用する認証方式です。</span><span class="sxs-lookup"><span data-stu-id="67c1d-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="67c1d-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="67c1d-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="67c1d-118">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="67c1d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="67c1d-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-120">プロキシをローカル アドレスで無視するかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="67c1d-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="67c1d-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="67c1d-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="67c1d-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="67c1d-122">Data type: string</span></span>  
  
 <span data-ttu-id="67c1d-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-124">URI の照合時にサービスに到達するため、ホスト名が使用されたかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="67c1d-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="67c1d-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="67c1d-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="67c1d-126">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="67c1d-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="67c1d-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-128">有効な場合は、HTTP 接続がアクティビティ レベルとは無関係に維持されます。</span><span class="sxs-lookup"><span data-stu-id="67c1d-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="67c1d-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="67c1d-129">MaxBufferSize</span></span>  
 <span data-ttu-id="67c1d-130">データ型 : sint32</span><span class="sxs-lookup"><span data-stu-id="67c1d-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="67c1d-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-132">バッファー プールの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="67c1d-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="67c1d-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="67c1d-133">ProxyAddress</span></span>  
 <span data-ttu-id="67c1d-134">データ型: string</span><span class="sxs-lookup"><span data-stu-id="67c1d-134">Data type: string</span></span>  
  
 <span data-ttu-id="67c1d-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-136">HTTP 要求に使用するプロキシのアドレスを格納する URI です。</span><span class="sxs-lookup"><span data-stu-id="67c1d-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="67c1d-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="67c1d-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="67c1d-138">データ型: string</span><span class="sxs-lookup"><span data-stu-id="67c1d-138">Data type: string</span></span>  
  
 <span data-ttu-id="67c1d-139">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-140">HTTP プロキシにより処理されているクライアント要求の認証に使用する認証方式です。</span><span class="sxs-lookup"><span data-stu-id="67c1d-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="67c1d-141">Realm</span><span class="sxs-lookup"><span data-stu-id="67c1d-141">Realm</span></span>  
 <span data-ttu-id="67c1d-142">データ型: string</span><span class="sxs-lookup"><span data-stu-id="67c1d-142">Data type: string</span></span>  
  
 <span data-ttu-id="67c1d-143">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-144">認証領域。</span><span class="sxs-lookup"><span data-stu-id="67c1d-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="67c1d-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="67c1d-145">TransferMode</span></span>  
 <span data-ttu-id="67c1d-146">データ型: string</span><span class="sxs-lookup"><span data-stu-id="67c1d-146">Data type: string</span></span>  
  
 <span data-ttu-id="67c1d-147">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-148">メッセージが要求や応答をバッファーするか、ストリーミングするかを指定する値です。</span><span class="sxs-lookup"><span data-stu-id="67c1d-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="67c1d-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="67c1d-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="67c1d-150">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="67c1d-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="67c1d-151">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-152">サーバー上で安全ではない接続共有を有効にするかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="67c1d-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="67c1d-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="67c1d-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="67c1d-154">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="67c1d-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="67c1d-155">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="67c1d-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67c1d-156">ユーザー固有の設定ではなく、コンピューター全体のプロキシ設定を使用するかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="67c1d-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c1d-157">必要条件</span><span class="sxs-lookup"><span data-stu-id="67c1d-157">Requirements</span></span>  
  
|<span data-ttu-id="67c1d-158">MOF</span><span class="sxs-lookup"><span data-stu-id="67c1d-158">MOF</span></span>|<span data-ttu-id="67c1d-159">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="67c1d-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="67c1d-160">名前空間</span><span class="sxs-lookup"><span data-stu-id="67c1d-160">Namespace</span></span>|<span data-ttu-id="67c1d-161">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="67c1d-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67c1d-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="67c1d-162">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
