---
title: <httpListener> 要素 (ネットワーク設定)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 8257b0311e18a21fbc04185f8297ee8e5f38b86b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592741"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="38f20-102">\<httpListener > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="38f20-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="38f20-103"><xref:System.Net.HttpListener>クラスで使用されるパラメータをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="38f20-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
 <span data-ttu-id="38f20-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="38f20-104">\<configuration></span></span>  
<span data-ttu-id="38f20-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="38f20-105">\<system.net></span></span>  
<span data-ttu-id="38f20-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="38f20-106">\<settings></span></span>  
<span data-ttu-id="38f20-107">\<httpListener></span><span class="sxs-lookup"><span data-stu-id="38f20-107">\<httpListener></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38f20-108">構文</span><span class="sxs-lookup"><span data-stu-id="38f20-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="38f20-109">型</span><span class="sxs-lookup"><span data-stu-id="38f20-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38f20-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="38f20-110">Attributes and Elements</span></span>  
 <span data-ttu-id="38f20-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="38f20-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38f20-112">属性</span><span class="sxs-lookup"><span data-stu-id="38f20-112">Attributes</span></span>  
  
|<span data-ttu-id="38f20-113">属性</span><span class="sxs-lookup"><span data-stu-id="38f20-113">Attribute</span></span>|<span data-ttu-id="38f20-114">説明</span><span class="sxs-lookup"><span data-stu-id="38f20-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38f20-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="38f20-115">unescapeRequestUrl</span></span>|<span data-ttu-id="38f20-116">場合を示すブール値、<xref:System.Net.HttpListener>インスタンスは、変換された URI ではなく生のエスケープ解除された URI を使用します。</span><span class="sxs-lookup"><span data-stu-id="38f20-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38f20-117">子要素</span><span class="sxs-lookup"><span data-stu-id="38f20-117">Child Elements</span></span>  
 <span data-ttu-id="38f20-118">なし。</span><span class="sxs-lookup"><span data-stu-id="38f20-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38f20-119">親要素</span><span class="sxs-lookup"><span data-stu-id="38f20-119">Parent Elements</span></span>  
  
|<span data-ttu-id="38f20-120">**要素**</span><span class="sxs-lookup"><span data-stu-id="38f20-120">**Element**</span></span>|<span data-ttu-id="38f20-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="38f20-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="38f20-122">settings</span><span class="sxs-lookup"><span data-stu-id="38f20-122">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="38f20-123"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="38f20-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38f20-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="38f20-124">Remarks</span></span>  
 <span data-ttu-id="38f20-125">**UnescapeRequestUrl**属性を示す場合<xref:System.Net.HttpListener>をパーセントでエンコードされた値は変換され、その他の正規化の手順を実行、変換された URI ではなく生のエスケープ解除された URI を使用します。</span><span class="sxs-lookup"><span data-stu-id="38f20-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="38f20-126">ときに、<xref:System.Net.HttpListener>インスタンスを介して要求を受け取ると、`http.sys`により指定された URI 文字列のインスタンスを作成しますが、サービス`http.sys`、としてそれを公開、<xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="38f20-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="38f20-127">`http.sys`サービスは 2 つの要求 URI の文字列を公開します。</span><span class="sxs-lookup"><span data-stu-id="38f20-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="38f20-128">生の URI</span><span class="sxs-lookup"><span data-stu-id="38f20-128">Raw URI</span></span>  
  
- <span data-ttu-id="38f20-129">変換された URI</span><span class="sxs-lookup"><span data-stu-id="38f20-129">Converted URI</span></span>  
  
 <span data-ttu-id="38f20-130">生の URI は、 <xref:System.Uri?displayProperty=nameWithType> HTTP 要求の要求行で提供されます。</span><span class="sxs-lookup"><span data-stu-id="38f20-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="38f20-131">によって提供された生の URI`http.sys`上記のように、要求は"パス"/です。</span><span class="sxs-lookup"><span data-stu-id="38f20-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="38f20-132">これは、次の HTTP 動詞がネットワーク経由で送信した文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="38f20-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="38f20-133">`http.sys`サービスは、HTTP 要求行で指定された URI を使用して、要求で提供される情報から変換された URI を作成しに、要求の配信元サーバーを決定する、ホスト ヘッダーを転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38f20-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="38f20-134">これは、一連の登録済みの URI プレフィックスを使用して要求からの情報を比較することによって行います。</span><span class="sxs-lookup"><span data-stu-id="38f20-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="38f20-135">この変換された URI は、HTTP Server SDK ドキュメントでは HTTP_COOKED_URL 構造と呼びます。</span><span class="sxs-lookup"><span data-stu-id="38f20-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="38f20-136">登録済みの URI プレフィックスを持つ要求を比較できるようにするには、するには、要求の正規化をいくつかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38f20-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="38f20-137">変換された URI 上のサンプルであるように。</span><span class="sxs-lookup"><span data-stu-id="38f20-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="38f20-138">`http.sys`サービスの結合、<xref:System.Uri.Host%2A?displayProperty=nameWithType>プロパティの値と、変換された URI を作成する要求の行の文字列。</span><span class="sxs-lookup"><span data-stu-id="38f20-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="38f20-139">さらに、`http.sys`と<xref:System.Uri?displayProperty=nameWithType>クラスも、次を行います。</span><span class="sxs-lookup"><span data-stu-id="38f20-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="38f20-140">すべてのパーセントでエンコードされた値エスケープ解除します。</span><span class="sxs-lookup"><span data-stu-id="38f20-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="38f20-141">Utf-16 文字表現に非 ASCII 文字をパーセントでエンコードに変換します。</span><span class="sxs-lookup"><span data-stu-id="38f20-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="38f20-142">Unicode の文字 (Unicode のエンコード %uxxxx 形式を使用) と、utf-8 と ANSI や DBCS 文字がサポートされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="38f20-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="38f20-143">パスの圧縮など、他の正規化の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="38f20-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="38f20-144">要求には、パーセントでエンコードされた値に使用されるエンコーディングに関する情報が含まれていない、以降は、パーセントでエンコードされた値を解析するだけで正しいエンコーディングを判断することはできません。</span><span class="sxs-lookup"><span data-stu-id="38f20-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="38f20-145">そのため`http.sys`プロセスを変更するための 2 つのレジストリ キーを提供します。</span><span class="sxs-lookup"><span data-stu-id="38f20-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="38f20-146">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="38f20-146">Registry Key</span></span>|<span data-ttu-id="38f20-147">既定値</span><span class="sxs-lookup"><span data-stu-id="38f20-147">Default Value</span></span>|<span data-ttu-id="38f20-148">説明</span><span class="sxs-lookup"><span data-stu-id="38f20-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="38f20-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="38f20-149">EnableNonUTF8</span></span>|<span data-ttu-id="38f20-150">1</span><span class="sxs-lookup"><span data-stu-id="38f20-150">1</span></span>|<span data-ttu-id="38f20-151">0 の場合、 `http.sys` UTF エンコードの Url のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="38f20-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="38f20-152">0 以外の場合`http.sys`も要求で ANSI でエンコードされたまたは DBCS でエンコードされた Url を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="38f20-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="38f20-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="38f20-153">FavorUTF8</span></span>|<span data-ttu-id="38f20-154">1</span><span class="sxs-lookup"><span data-stu-id="38f20-154">1</span></span>|<span data-ttu-id="38f20-155">0 以外の場合`http.sys`最初をデコードする URL を utf-8 として; 変換に失敗したし、EnableNonUTF8 が 0 以外の場合と常に、Http.sys、ANSI または DBCS とデコードを試みます。</span><span class="sxs-lookup"><span data-stu-id="38f20-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="38f20-156">0 の場合 (および EnableNonUTF8 が 0 以外)、`http.sys`を ANSI または DBCS; としてデコードする試行が成功しなかった、utf-8 変換を試みます。</span><span class="sxs-lookup"><span data-stu-id="38f20-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="38f20-157">ときに<xref:System.Net.HttpListener>要求を受信から変換された URI を使用して`http.sys`への入力として、<xref:System.Net.HttpListenerRequest.Url%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="38f20-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="38f20-158">Uri の文字と数字以外の文字をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38f20-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="38f20-159">例としては、次の URI は、お客様の顧客情報を取得するために使用番号「1/3812」。</span><span class="sxs-lookup"><span data-stu-id="38f20-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="38f20-160">Uri (%2f) でパーセント エンコード スラッシュに注意してください。</span><span class="sxs-lookup"><span data-stu-id="38f20-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="38f20-161">これは、スラッシュ文字を表すデータとパス区切り記号ではなくこのケースであるため、必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="38f20-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="38f20-162">Uri のコンス トラクターに文字列を渡すことは、次の URI につながります。</span><span class="sxs-lookup"><span data-stu-id="38f20-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="38f20-163">パスはセグメントに分割することで、次の要素になります。</span><span class="sxs-lookup"><span data-stu-id="38f20-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="38f20-164">これは、要求の送信元の目的ではありません。</span><span class="sxs-lookup"><span data-stu-id="38f20-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="38f20-165">場合、 **unescapeRequestUrl**属性に設定されて**false**、その後、<xref:System.Net.HttpListener>要求を受信から変換された URI ではなく生の URI を使用して`http.sys`への入力として<xref:System.Net.HttpListenerRequest.Url%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="38f20-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="38f20-166">既定値、 **unescapeRequestUrl**属性が**true**します。</span><span class="sxs-lookup"><span data-stu-id="38f20-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="38f20-167"><xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A>プロパティを使用しての現在の値を取得すること、 **unescapeRequestUrl**該当する構成ファイルからの属性。</span><span class="sxs-lookup"><span data-stu-id="38f20-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38f20-168">例</span><span class="sxs-lookup"><span data-stu-id="38f20-168">Example</span></span>  
 <span data-ttu-id="38f20-169">次の例は、構成する方法を示します、<xref:System.Net.HttpListener>から変換された URI ではなく生の URI を使用して要求を受信時`http.sys`への入力として、<xref:System.Net.HttpListenerRequest.Url%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="38f20-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="38f20-170">要素情報</span><span class="sxs-lookup"><span data-stu-id="38f20-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="38f20-171">名前空間</span><span class="sxs-lookup"><span data-stu-id="38f20-171">Namespace</span></span>|<span data-ttu-id="38f20-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="38f20-172">System.Net</span></span>|  
|<span data-ttu-id="38f20-173">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="38f20-173">Schema Name</span></span>||  
|<span data-ttu-id="38f20-174">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="38f20-174">Validation File</span></span>||  
|<span data-ttu-id="38f20-175">空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="38f20-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="38f20-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="38f20-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="38f20-177">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="38f20-177">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
