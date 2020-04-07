---
title: ネットワークの構成設定
description: .NET Core アプリのネットワークを構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: f5ea47f0444a911dc2347a66817cabf585fd8e70
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635422"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="5a73b-103">ネットワークのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="5a73b-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="5a73b-104">HTTP/2 プロトコル</span><span class="sxs-lookup"><span data-stu-id="5a73b-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="5a73b-105">HTTP/2 プロトコルのサポートを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="5a73b-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="5a73b-106">既定:無効 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="5a73b-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="5a73b-107">.NET Core 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a73b-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="5a73b-108">設定の名前</span><span class="sxs-lookup"><span data-stu-id="5a73b-108">Setting name</span></span> | <span data-ttu-id="5a73b-109">値</span><span class="sxs-lookup"><span data-stu-id="5a73b-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5a73b-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5a73b-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="5a73b-111">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="5a73b-111">`false` - disabled</span></span><br/><span data-ttu-id="5a73b-112">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="5a73b-112">`true` - enabled</span></span> |
| <span data-ttu-id="5a73b-113">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="5a73b-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="5a73b-114">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="5a73b-114">`0` - disabled</span></span><br/><span data-ttu-id="5a73b-115">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="5a73b-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="5a73b-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="5a73b-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="5a73b-117"><xref:System.Net.Http.HttpClient> などのハイレベル ネットワーク API で <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> を使用するか、または [libcurl](https://curl.haxx.se/libcurl/)に基づく <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> の実装を使用するかを構成します。</span><span class="sxs-lookup"><span data-stu-id="5a73b-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="5a73b-118">既定:<xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> を使用します (`true`)。</span><span class="sxs-lookup"><span data-stu-id="5a73b-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="5a73b-119">この設定は、<xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> メソッドを呼び出すことによりプログラムで構成できます。</span><span class="sxs-lookup"><span data-stu-id="5a73b-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="5a73b-120">設定の名前</span><span class="sxs-lookup"><span data-stu-id="5a73b-120">Setting name</span></span> | <span data-ttu-id="5a73b-121">値</span><span class="sxs-lookup"><span data-stu-id="5a73b-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5a73b-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5a73b-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="5a73b-123">`true` - <xref:System.Net.Http.SocketsHttpHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="5a73b-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="5a73b-124">`false` - <xref:System.Net.Http.HttpClientHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="5a73b-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="5a73b-125">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="5a73b-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="5a73b-126">`1` - <xref:System.Net.Http.SocketsHttpHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="5a73b-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="5a73b-127">`0` - <xref:System.Net.Http.HttpClientHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="5a73b-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |

> [!NOTE]
> <span data-ttu-id="5a73b-128">.NET 5 以降では、`System.Net.Http.UseSocketsHttpHandler` 設定は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5a73b-128">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
