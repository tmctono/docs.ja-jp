---
title: <httpWebRequest> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 722b2f726c9085f6dee6bad82044da3011b98702
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169300"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="8ec10-102">\<httpWebRequest > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="8ec10-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="8ec10-103">Web 要求のパラメーターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="8ec10-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8ec10-104">\<configuration></span></span>  
<span data-ttu-id="8ec10-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="8ec10-105">\<system.net></span></span>  
<span data-ttu-id="8ec10-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="8ec10-106">\<settings></span></span>  
<span data-ttu-id="8ec10-107">\<httpWebRequest></span><span class="sxs-lookup"><span data-stu-id="8ec10-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec10-108">構文</span><span class="sxs-lookup"><span data-stu-id="8ec10-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ec10-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8ec10-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8ec10-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ec10-111">属性</span><span class="sxs-lookup"><span data-stu-id="8ec10-111">Attributes</span></span>  
  
|<span data-ttu-id="8ec10-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="8ec10-112">**Attribute**</span></span>|<span data-ttu-id="8ec10-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="8ec10-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="8ec10-114">(キロバイト単位)、応答ヘッダーの最大長を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="8ec10-115">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="8ec10-115">The default is 64.</span></span> <span data-ttu-id="8ec10-116">値-1 は、応答ヘッダーにサイズの上限が設定されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="8ec10-117">(キロバイト単位)、エラー応答の最大長を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="8ec10-118">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="8ec10-118">The default is 64.</span></span> <span data-ttu-id="8ec10-119">値-1 はエラー応答のサイズの上限が設定されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="8ec10-120">アップロードの最大長 (バイト単位)、未承認のエラー コードへの応答を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="8ec10-121">既定値は -1 です。</span><span class="sxs-lookup"><span data-stu-id="8ec10-121">The default is -1.</span></span> <span data-ttu-id="8ec10-122">値-1 は、アップロードのサイズの上限が設定されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="8ec10-123">安全でないヘッダーの解析が有効になっているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="8ec10-124">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="8ec10-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ec10-125">子要素</span><span class="sxs-lookup"><span data-stu-id="8ec10-125">Child Elements</span></span>  
 <span data-ttu-id="8ec10-126">なし。</span><span class="sxs-lookup"><span data-stu-id="8ec10-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ec10-127">親要素</span><span class="sxs-lookup"><span data-stu-id="8ec10-127">Parent Elements</span></span>  
  
|<span data-ttu-id="8ec10-128">**要素**</span><span class="sxs-lookup"><span data-stu-id="8ec10-128">**Element**</span></span>|<span data-ttu-id="8ec10-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="8ec10-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8ec10-130">settings</span><span class="sxs-lookup"><span data-stu-id="8ec10-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="8ec10-131"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ec10-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="8ec10-132">Remarks</span></span>  
 <span data-ttu-id="8ec10-133">既定では、.NET Framework は URI 解析の RFC 2616 を厳密には適用します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="8ec10-134">これにより、禁止されているフィールドの一部のサーバー応答が制御文字を含めることができます、<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>をスローするメソッド、<xref:System.Net.WebException>します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="8ec10-135">場合**useUnsafeHeaderParsing**に設定されている**true**、<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>スローされません。 ただし、この場合、アプリケーションがいくつかの形式の URI 解析攻撃を受けやすくなります。</span><span class="sxs-lookup"><span data-stu-id="8ec10-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="8ec10-136">応答に制御文字が含まれないように、サーバーを変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8ec10-137">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="8ec10-137">Configuration Files</span></span>  
 <span data-ttu-id="8ec10-138">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ec10-139">例</span><span class="sxs-lookup"><span data-stu-id="8ec10-139">Example</span></span>  
 <span data-ttu-id="8ec10-140">次の例は、大きい値を指定する方法を示しています。 標準ヘッダーの最大の長さよりもします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ec10-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ec10-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="8ec10-142">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="8ec10-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
