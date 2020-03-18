---
title: ネットワークの構成設定
description: .NET Core アプリのネットワークを構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 622c4afbd36d3d9004edbd9219145fa9e5d326ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74998835"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="61af0-103">ネットワークのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="61af0-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="61af0-104">HTTP/2 プロトコル</span><span class="sxs-lookup"><span data-stu-id="61af0-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="61af0-105">HTTP/2 プロトコルのサポートを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="61af0-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="61af0-106">既定:無効 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="61af0-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="61af0-107">.NET Core 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="61af0-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="61af0-108">設定の名前</span><span class="sxs-lookup"><span data-stu-id="61af0-108">Setting name</span></span> | <span data-ttu-id="61af0-109">値</span><span class="sxs-lookup"><span data-stu-id="61af0-109">Values</span></span> |
| - | - |
| <span data-ttu-id="61af0-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="61af0-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="61af0-111">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="61af0-111">`false` - disabled</span></span><br/><span data-ttu-id="61af0-112">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="61af0-112">`true` - enabled</span></span> |
| <span data-ttu-id="61af0-113">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="61af0-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="61af0-114">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="61af0-114">`0` - disabled</span></span><br/><span data-ttu-id="61af0-115">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="61af0-115">`1` - enabled</span></span> |

## <a name="sockets-http-handler"></a><span data-ttu-id="61af0-116">ソケットの HTTP ハンドラー</span><span class="sxs-lookup"><span data-stu-id="61af0-116">Sockets HTTP handler</span></span>

- <span data-ttu-id="61af0-117"><xref:System.Net.Http.HttpClient> などのハイレベル ネットワーク API で <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> を使用するか、または [libcurl](https://curl.haxx.se/libcurl/)に基づく <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> の実装を使用するかを構成します。</span><span class="sxs-lookup"><span data-stu-id="61af0-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="61af0-118">既定:<xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> を使用します (`true`)。</span><span class="sxs-lookup"><span data-stu-id="61af0-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="61af0-119">この設定は、<xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> メソッドを呼び出すことによりプログラムで構成できます。</span><span class="sxs-lookup"><span data-stu-id="61af0-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="61af0-120">設定の名前</span><span class="sxs-lookup"><span data-stu-id="61af0-120">Setting name</span></span> | <span data-ttu-id="61af0-121">値</span><span class="sxs-lookup"><span data-stu-id="61af0-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="61af0-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="61af0-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="61af0-123">`true` - <xref:System.Net.Http.SocketsHttpHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="61af0-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="61af0-124">`false` - <xref:System.Net.Http.HttpClientHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="61af0-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="61af0-125">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="61af0-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="61af0-126">`1` - <xref:System.Net.Http.SocketsHttpHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="61af0-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="61af0-127">`0` - <xref:System.Net.Http.HttpClientHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="61af0-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
