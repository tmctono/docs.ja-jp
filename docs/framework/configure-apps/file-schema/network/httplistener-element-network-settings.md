---
title: <httpListener> 要素 (ネットワーク設定)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 0054be3d2002e4ea5247f25d8094386ac7242422
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088373"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="e0cb4-102">\<httpListener > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="e0cb4-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="e0cb4-103"><xref:System.Net.HttpListener> クラスによって使用されるパラメーターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  

<span data-ttu-id="e0cb4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e0cb4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e0cb4-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e0cb4-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="e0cb4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<設定 >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e0cb4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="e0cb4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**httpListener >**</span><span class="sxs-lookup"><span data-stu-id="e0cb4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e0cb4-108">構文</span><span class="sxs-lookup"><span data-stu-id="e0cb4-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="e0cb4-109">[種類]</span><span class="sxs-lookup"><span data-stu-id="e0cb4-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0cb4-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e0cb4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e0cb4-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0cb4-112">属性</span><span class="sxs-lookup"><span data-stu-id="e0cb4-112">Attributes</span></span>  
  
|<span data-ttu-id="e0cb4-113">属性</span><span class="sxs-lookup"><span data-stu-id="e0cb4-113">Attribute</span></span>|<span data-ttu-id="e0cb4-114">説明</span><span class="sxs-lookup"><span data-stu-id="e0cb4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0cb4-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="e0cb4-115">unescapeRequestUrl</span></span>|<span data-ttu-id="e0cb4-116"><xref:System.Net.HttpListener> インスタンスが、変換された URI ではなく、未加工のエスケープされていない URI を使用するかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0cb4-117">子要素</span><span class="sxs-lookup"><span data-stu-id="e0cb4-117">Child Elements</span></span>  
 <span data-ttu-id="e0cb4-118">なし。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0cb4-119">親要素</span><span class="sxs-lookup"><span data-stu-id="e0cb4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e0cb4-120">**要素**</span><span class="sxs-lookup"><span data-stu-id="e0cb4-120">**Element**</span></span>|<span data-ttu-id="e0cb4-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="e0cb4-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e0cb4-122">settings</span><span class="sxs-lookup"><span data-stu-id="e0cb4-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="e0cb4-123"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0cb4-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="e0cb4-124">Remarks</span></span>  
 <span data-ttu-id="e0cb4-125">**UnescapeRequestUrl**属性は、パーセントエンコードされた値が変換され、その他の正規化ステップが実行される場合に、<xref:System.Net.HttpListener> が、変換後の uri ではなく、未加工のエスケープされていない uri を使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="e0cb4-126">`http.sys` サービスを介して <xref:System.Net.HttpListener> インスタンスが要求を受け取ると、`http.sys`によって提供される URI 文字列のインスタンスが作成され、<xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> プロパティとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="e0cb4-127">`http.sys` サービスは、次の2つの要求 URI 文字列を公開します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="e0cb4-128">未加工の URI</span><span class="sxs-lookup"><span data-stu-id="e0cb4-128">Raw URI</span></span>  
  
- <span data-ttu-id="e0cb4-129">変換された URI</span><span class="sxs-lookup"><span data-stu-id="e0cb4-129">Converted URI</span></span>  
  
 <span data-ttu-id="e0cb4-130">未加工 URI は、HTTP 要求の要求行に指定された <xref:System.Uri?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="e0cb4-131">前述の要求に対して `http.sys` によって提供される未加工の URI は、"/path/" です。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="e0cb4-132">これは、ネットワーク経由で送信された HTTP 動詞に続く文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="e0cb4-133">`http.sys` サービスは、HTTP 要求行に指定された URI とホストヘッダーを使用して要求で提供される情報から変換された URI を作成し、要求の転送先となる配信元サーバーを決定します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="e0cb4-134">これは、要求の情報を一連の登録済み URI プレフィックスと比較することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="e0cb4-135">HTTP Server SDK のドキュメントでは、この変換された URI を HTTP_COOKED_URL 構造として参照します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="e0cb4-136">要求を登録済みの URI プレフィックスと比較できるようにするには、要求の正規化を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="e0cb4-137">上記のサンプルの場合、変換後の URI は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="e0cb4-138">`http.sys` サービスは、<xref:System.Uri.Host%2A?displayProperty=nameWithType> プロパティ値と要求行の文字列を組み合わせて、変換された URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="e0cb4-139">さらに、`http.sys` と <xref:System.Uri?displayProperty=nameWithType> クラスは次のことも行います。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="e0cb4-140">パーセントでエンコードされたすべての値をエスケープ解除します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="e0cb4-141">パーセントでエンコードされた非 ASCII 文字を UTF-16 文字表現に変換します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="e0cb4-142">UTF-8 および ANSI/DBCS 文字は、Unicode 文字 (% uXXXX 形式を使用した Unicode エンコード) でもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="e0cb4-143">パスの圧縮など、その他の正規化手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="e0cb4-144">パーセントでエンコードされた値に使用されるエンコーディングに関する情報が要求に含まれていないため、パーセントでエンコードされた値を解析するだけで、正しいエンコーディングを判断できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="e0cb4-145">そのため `http.sys` には、プロセスを変更するための2つのレジストリキーがあります。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="e0cb4-146">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="e0cb4-146">Registry Key</span></span>|<span data-ttu-id="e0cb4-147">既定値</span><span class="sxs-lookup"><span data-stu-id="e0cb4-147">Default Value</span></span>|<span data-ttu-id="e0cb4-148">説明</span><span class="sxs-lookup"><span data-stu-id="e0cb4-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="e0cb4-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="e0cb4-149">EnableNonUTF8</span></span>|<span data-ttu-id="e0cb4-150">1</span><span class="sxs-lookup"><span data-stu-id="e0cb4-150">1</span></span>|<span data-ttu-id="e0cb4-151">ゼロの場合、`http.sys` は UTF-8 でエンコードされた Url のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="e0cb4-152">0以外の場合、`http.sys` は、要求で ANSI エンコードまたは DBCS でエンコードされた Url も受け入れます。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="e0cb4-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="e0cb4-153">FavorUTF8</span></span>|<span data-ttu-id="e0cb4-154">1</span><span class="sxs-lookup"><span data-stu-id="e0cb4-154">1</span></span>|<span data-ttu-id="e0cb4-155">0以外の場合、`http.sys` は常に UTF-8 として URL をデコードしようとします。この変換が失敗し、EnableNonUTF8 が0以外の場合は、http.sys は ANSI または DBCS としてデコードしようとします。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="e0cb4-156">0 (および EnableNonUTF8 が0以外) の場合、`http.sys` は ANSI または DBCS としてデコードしようとします。これが成功しなかった場合は、UTF-8 変換が試行されます。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="e0cb4-157"><xref:System.Net.HttpListener> が要求を受信すると、`http.sys` の変換された URI を <xref:System.Net.HttpListenerRequest.Url%2A> プロパティへの入力として使用します。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="e0cb4-158">Uri の文字と数字以外の文字をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="e0cb4-159">例として、次の URI があります。これは、顧客番号 "1/3812" の顧客情報を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="e0cb4-160">Uri (% 2F) のパーセントでエンコードされたスラッシュに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="e0cb4-161">この場合は、スラッシュ文字がパス区切り記号ではなく、データを表すために必要です。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="e0cb4-162">文字列を Uri コンストラクターに渡すと、次の URI になります。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="e0cb4-163">パスをセグメントに分割すると、次の要素が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="e0cb4-164">これは、要求の送信者の意図ではありません。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="e0cb4-165">**UnescapeRequestUrl**属性が**false**に設定されている場合、<xref:System.Net.HttpListener> が要求を受信すると、`http.sys` の変換された uri ではなく、未加工の uri が <xref:System.Net.HttpListenerRequest.Url%2A> プロパティに入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="e0cb4-166">**UnescapeRequestUrl**属性の既定値は**true**です。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="e0cb4-167"><xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> プロパティは、適用可能な構成ファイルから**unescapeRequestUrl**属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0cb4-168">例</span><span class="sxs-lookup"><span data-stu-id="e0cb4-168">Example</span></span>  
 <span data-ttu-id="e0cb4-169">次の例は、<xref:System.Net.HttpListenerRequest.Url%2A> プロパティへの入力として `http.sys` から変換された URI ではなく、未加工の URI を使用するように要求を受け取ったときに <xref:System.Net.HttpListener> クラスを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0cb4-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="e0cb4-170">要素情報</span><span class="sxs-lookup"><span data-stu-id="e0cb4-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="e0cb4-171">Namespace</span><span class="sxs-lookup"><span data-stu-id="e0cb4-171">Namespace</span></span>|<span data-ttu-id="e0cb4-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="e0cb4-172">System.Net</span></span>|  
|<span data-ttu-id="e0cb4-173">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="e0cb4-173">Schema Name</span></span>||  
|<span data-ttu-id="e0cb4-174">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="e0cb4-174">Validation File</span></span>||  
|<span data-ttu-id="e0cb4-175">空にすることができます</span><span class="sxs-lookup"><span data-stu-id="e0cb4-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="e0cb4-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0cb4-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="e0cb4-177">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e0cb4-177">Network Settings Schema</span></span>](index.md)
