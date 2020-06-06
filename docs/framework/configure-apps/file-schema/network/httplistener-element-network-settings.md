---
title: <httpListener> 要素 (ネットワーク設定)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 0054be3d2002e4ea5247f25d8094386ac7242422
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088373"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="968d3-102">\<httpListener> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="968d3-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="968d3-103">クラスによって使用されるパラメーターをカスタマイズ <xref:System.Net.HttpListener> します。</span><span class="sxs-lookup"><span data-stu-id="968d3-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**

## <a name="syntax"></a><span data-ttu-id="968d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="968d3-104">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="968d3-105">Type</span><span class="sxs-lookup"><span data-stu-id="968d3-105">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="968d3-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="968d3-106">Attributes and Elements</span></span>  
 <span data-ttu-id="968d3-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="968d3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="968d3-108">属性</span><span class="sxs-lookup"><span data-stu-id="968d3-108">Attributes</span></span>  
  
|<span data-ttu-id="968d3-109">属性</span><span class="sxs-lookup"><span data-stu-id="968d3-109">Attribute</span></span>|<span data-ttu-id="968d3-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="968d3-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="968d3-111">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="968d3-111">unescapeRequestUrl</span></span>|<span data-ttu-id="968d3-112">インスタンスが、 <xref:System.Net.HttpListener> 変換後の uri ではなく、未加工のエスケープされていない uri を使用するかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="968d3-112">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="968d3-113">子要素</span><span class="sxs-lookup"><span data-stu-id="968d3-113">Child Elements</span></span>  
 <span data-ttu-id="968d3-114">なし。</span><span class="sxs-lookup"><span data-stu-id="968d3-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="968d3-115">親要素</span><span class="sxs-lookup"><span data-stu-id="968d3-115">Parent Elements</span></span>  
  
|<span data-ttu-id="968d3-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="968d3-116">**Element**</span></span>|<span data-ttu-id="968d3-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="968d3-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="968d3-118">設定</span><span class="sxs-lookup"><span data-stu-id="968d3-118">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="968d3-119"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="968d3-119">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="968d3-120">解説</span><span class="sxs-lookup"><span data-stu-id="968d3-120">Remarks</span></span>  
 <span data-ttu-id="968d3-121">**UnescapeRequestUrl**属性は、が変換された uri では <xref:System.Net.HttpListener> なく、生のエスケープされていない uri を使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="968d3-121">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="968d3-122">インスタンスは、 <xref:System.Net.HttpListener> サービスを介して要求を受け取ると、 `http.sys` によって提供される URI 文字列のインスタンスを作成 `http.sys` し、プロパティとして公開し <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="968d3-122">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="968d3-123">サービスは、 `http.sys` 次の2つの要求 URI 文字列を公開します。</span><span class="sxs-lookup"><span data-stu-id="968d3-123">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="968d3-124">未加工の URI</span><span class="sxs-lookup"><span data-stu-id="968d3-124">Raw URI</span></span>  
  
- <span data-ttu-id="968d3-125">変換された URI</span><span class="sxs-lookup"><span data-stu-id="968d3-125">Converted URI</span></span>  
  
 <span data-ttu-id="968d3-126">未加工 URI は、 <xref:System.Uri?displayProperty=nameWithType> HTTP 要求の要求行で指定されるです。</span><span class="sxs-lookup"><span data-stu-id="968d3-126">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="968d3-127">前述の要求に対してによって提供される未加工の URI `http.sys` は、"/path/" です。</span><span class="sxs-lookup"><span data-stu-id="968d3-127">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="968d3-128">これは、ネットワーク経由で送信された HTTP 動詞に続く文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="968d3-128">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="968d3-129">サービスは、 `http.sys` HTTP 要求行に指定された uri とホストヘッダーを使用して、要求で提供される情報から変換された uri を作成し、要求の転送先となる配信元サーバーを決定します。</span><span class="sxs-lookup"><span data-stu-id="968d3-129">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="968d3-130">これは、要求の情報を一連の登録済み URI プレフィックスと比較することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="968d3-130">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="968d3-131">HTTP Server SDK のドキュメントでは、この変換された URI を HTTP_COOKED_URL 構造として参照します。</span><span class="sxs-lookup"><span data-stu-id="968d3-131">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="968d3-132">要求を登録済みの URI プレフィックスと比較できるようにするには、要求の正規化を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="968d3-132">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="968d3-133">上記のサンプルの場合、変換後の URI は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="968d3-133">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="968d3-134">サービスは、 `http.sys` <xref:System.Uri.Host%2A?displayProperty=nameWithType> 要求行にプロパティ値と文字列を結合して、変換された URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="968d3-134">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="968d3-135">さらに、 `http.sys` クラスは <xref:System.Uri?displayProperty=nameWithType> 次のことも行います。</span><span class="sxs-lookup"><span data-stu-id="968d3-135">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="968d3-136">パーセントでエンコードされたすべての値をエスケープ解除します。</span><span class="sxs-lookup"><span data-stu-id="968d3-136">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="968d3-137">パーセントでエンコードされた非 ASCII 文字を UTF-16 文字表現に変換します。</span><span class="sxs-lookup"><span data-stu-id="968d3-137">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="968d3-138">UTF-8 および ANSI/DBCS 文字は、Unicode 文字 (% uXXXX 形式を使用した Unicode エンコード) でもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="968d3-138">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="968d3-139">パスの圧縮など、その他の正規化手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="968d3-139">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="968d3-140">パーセントでエンコードされた値に使用されるエンコーディングに関する情報が要求に含まれていないため、パーセントでエンコードされた値を解析するだけで、正しいエンコーディングを判断できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="968d3-140">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="968d3-141">このため `http.sys` 、プロセスを変更するには、次の2つのレジストリキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="968d3-141">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="968d3-142">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="968d3-142">Registry Key</span></span>|<span data-ttu-id="968d3-143">Default value</span><span class="sxs-lookup"><span data-stu-id="968d3-143">Default Value</span></span>|<span data-ttu-id="968d3-144">説明</span><span class="sxs-lookup"><span data-stu-id="968d3-144">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="968d3-145">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="968d3-145">EnableNonUTF8</span></span>|<span data-ttu-id="968d3-146">1</span><span class="sxs-lookup"><span data-stu-id="968d3-146">1</span></span>|<span data-ttu-id="968d3-147">ゼロの場合、は `http.sys` utf-8 でエンコードされた url のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="968d3-147">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="968d3-148">0以外の場合、 `http.sys` は、要求で ANSI エンコードまたは DBCS でエンコードされた url も受け入れます。</span><span class="sxs-lookup"><span data-stu-id="968d3-148">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="968d3-149">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="968d3-149">FavorUTF8</span></span>|<span data-ttu-id="968d3-150">1</span><span class="sxs-lookup"><span data-stu-id="968d3-150">1</span></span>|<span data-ttu-id="968d3-151">0以外の場合、は `http.sys` 常に utf-8 として URL をデコードしようとします。変換に失敗し、EnableNonUTF8 が0以外の場合は、http.sys は ANSI または DBCS としてデコードしようとします。</span><span class="sxs-lookup"><span data-stu-id="968d3-151">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="968d3-152">ゼロ (および EnableNonUTF8 が0以外) の場合、は `http.sys` ANSI または DBCS としてデコードしようとします。成功しなかった場合は、utf-8 変換を試行します。</span><span class="sxs-lookup"><span data-stu-id="968d3-152">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="968d3-153">は、要求を受信すると、変換された <xref:System.Net.HttpListener> URI をから `http.sys` プロパティへの入力として使用し <xref:System.Net.HttpListenerRequest.Url%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="968d3-153">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="968d3-154">Uri の文字と数字以外の文字をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="968d3-154">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="968d3-155">例として、次の URI があります。これは、顧客番号 "1/3812" の顧客情報を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="968d3-155">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="968d3-156">Uri (% 2F) のパーセントでエンコードされたスラッシュに注意してください。</span><span class="sxs-lookup"><span data-stu-id="968d3-156">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="968d3-157">この場合は、スラッシュ文字がパス区切り記号ではなく、データを表すために必要です。</span><span class="sxs-lookup"><span data-stu-id="968d3-157">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="968d3-158">文字列を Uri コンストラクターに渡すと、次の URI になります。</span><span class="sxs-lookup"><span data-stu-id="968d3-158">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="968d3-159">パスをセグメントに分割すると、次の要素が生成されます。</span><span class="sxs-lookup"><span data-stu-id="968d3-159">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="968d3-160">これは、要求の送信者の意図ではありません。</span><span class="sxs-lookup"><span data-stu-id="968d3-160">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="968d3-161">**UnescapeRequestUrl**属性が**false**に設定されている場合、が要求を受信すると、から変換された uri ではなく、 <xref:System.Net.HttpListener> 未加工の uri が `http.sys` プロパティへの入力として使用され <xref:System.Net.HttpListenerRequest.Url%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="968d3-161">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="968d3-162">**UnescapeRequestUrl**属性の既定値は**true**です。</span><span class="sxs-lookup"><span data-stu-id="968d3-162">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="968d3-163">プロパティは、 <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> 適用可能な構成ファイルから**unescapeRequestUrl**属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="968d3-163">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="968d3-164">例</span><span class="sxs-lookup"><span data-stu-id="968d3-164">Example</span></span>  
 <span data-ttu-id="968d3-165">次の例は、変換され <xref:System.Net.HttpListener> た uri ではなく、未加工の uri を使用するように要求を受け取ったときに、プロパティへの入力としてクラスを構成する方法を示して `http.sys` <xref:System.Net.HttpListenerRequest.Url%2A> います。</span><span class="sxs-lookup"><span data-stu-id="968d3-165">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="968d3-166">要素情報</span><span class="sxs-lookup"><span data-stu-id="968d3-166">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="968d3-167">名前空間</span><span class="sxs-lookup"><span data-stu-id="968d3-167">Namespace</span></span>|<span data-ttu-id="968d3-168">System.Net</span><span class="sxs-lookup"><span data-stu-id="968d3-168">System.Net</span></span>|  
|<span data-ttu-id="968d3-169">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="968d3-169">Schema Name</span></span>||  
|<span data-ttu-id="968d3-170">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="968d3-170">Validation File</span></span>||  
|<span data-ttu-id="968d3-171">空にすることができます</span><span class="sxs-lookup"><span data-stu-id="968d3-171">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="968d3-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="968d3-172">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="968d3-173">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="968d3-173">Network Settings Schema</span></span>](index.md)
