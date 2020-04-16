---
title: ネットワークの構成設定
description: .NET Core アプリのネットワークを構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 8d02087ad7260cc78c096090bf3b06a716d34678
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989104"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="36824-103">ネットワークのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="36824-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="36824-104">HTTP/2 プロトコル</span><span class="sxs-lookup"><span data-stu-id="36824-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="36824-105">HTTP/2 プロトコルのサポートを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="36824-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="36824-106">既定:無効 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="36824-106">Default: Disabled (`false`).</span></span>

- <span data-ttu-id="36824-107">.NET Core 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="36824-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="36824-108">設定の名前</span><span class="sxs-lookup"><span data-stu-id="36824-108">Setting name</span></span> | <span data-ttu-id="36824-109">値</span><span class="sxs-lookup"><span data-stu-id="36824-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="36824-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="36824-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="36824-111">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="36824-111">`false` - disabled</span></span><br/><span data-ttu-id="36824-112">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="36824-112">`true` - enabled</span></span> |
| <span data-ttu-id="36824-113">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="36824-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="36824-114">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="36824-114">`0` - disabled</span></span><br/><span data-ttu-id="36824-115">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="36824-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="36824-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="36824-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="36824-117"><xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> が <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 以前の HTTP プロトコル スタック (Windows と `CurlHandler` では <xref:System.Net.Http.WinHttpHandler>、Linux では [libcurl](https://curl.haxx.se/libcurl/) の上位に実装された内部クラス) を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="36824-117">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="36824-118"><xref:System.Net.Http.HttpClientHandler> クラスを直接インスタンス化するのではなく、高レベルのネットワーク API を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36824-118">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="36824-119">この設定は、<xref:System.Net.Http.HttpClient> や [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)) などの高レベル ネットワーク API で使用される HTTP プロトコル スタックにも影響します。</span><span class="sxs-lookup"><span data-stu-id="36824-119">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="36824-120">既定:<xref:System.Net.Http.SocketsHttpHandler> を使用します (`true`)。</span><span class="sxs-lookup"><span data-stu-id="36824-120">Default: Use <xref:System.Net.Http.SocketsHttpHandler> (`true`).</span></span>

- <span data-ttu-id="36824-121">この設定は、<xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> メソッドを呼び出すことによりプログラムで構成できます。</span><span class="sxs-lookup"><span data-stu-id="36824-121">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="36824-122">設定の名前</span><span class="sxs-lookup"><span data-stu-id="36824-122">Setting name</span></span> | <span data-ttu-id="36824-123">値</span><span class="sxs-lookup"><span data-stu-id="36824-123">Values</span></span> |
| - | - | - |
| <span data-ttu-id="36824-124">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="36824-124">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="36824-125">`true` - <xref:System.Net.Http.SocketsHttpHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="36824-125">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="36824-126">`false` - Windows では <xref:System.Net.Http.WinHttpHandler>、Linux では [libcurl](https://curl.haxx.se/libcurl/) の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="36824-126">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="36824-127">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="36824-127">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="36824-128">`1` - <xref:System.Net.Http.SocketsHttpHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="36824-128">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="36824-129">`0` - Windows では <xref:System.Net.Http.WinHttpHandler>、Linux では [libcurl](https://curl.haxx.se/libcurl/) の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="36824-129">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="36824-130">.NET 5 以降では、`System.Net.Http.UseSocketsHttpHandler` 設定は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="36824-130">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
