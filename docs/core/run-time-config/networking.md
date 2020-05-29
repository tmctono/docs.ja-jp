---
title: ネットワークの構成設定
description: .NET Core アプリのネットワークを構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6b5e03b127f95911b712b66c0be8a4f5a2929fc2
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761942"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="dcc85-103">ネットワークのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="dcc85-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="dcc85-104">HTTP/2 プロトコル</span><span class="sxs-lookup"><span data-stu-id="dcc85-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="dcc85-105">HTTP/2 プロトコルのサポートを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="dcc85-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="dcc85-106">この設定を省略した場合、HTTP/2 プロトコルのサポートは無効になります。</span><span class="sxs-lookup"><span data-stu-id="dcc85-106">If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="dcc85-107">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="dcc85-107">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="dcc85-108">.NET Core 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dcc85-108">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="dcc85-109">設定の名前</span><span class="sxs-lookup"><span data-stu-id="dcc85-109">Setting name</span></span> | <span data-ttu-id="dcc85-110">値</span><span class="sxs-lookup"><span data-stu-id="dcc85-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dcc85-111">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="dcc85-111">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="dcc85-112">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="dcc85-112">`false` - disabled</span></span><br/><span data-ttu-id="dcc85-113">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="dcc85-113">`true` - enabled</span></span> |
| <span data-ttu-id="dcc85-114">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="dcc85-114">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="dcc85-115">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="dcc85-115">`0` - disabled</span></span><br/><span data-ttu-id="dcc85-116">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="dcc85-116">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="dcc85-117">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="dcc85-117">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="dcc85-118"><xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> が <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 以前の HTTP プロトコル スタック (Windows と `CurlHandler` では <xref:System.Net.Http.WinHttpHandler>、Linux では [libcurl](https://curl.haxx.se/libcurl/) の上位に実装された内部クラス) を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="dcc85-118">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="dcc85-119"><xref:System.Net.Http.HttpClientHandler> クラスを直接インスタンス化するのではなく、高レベルのネットワーク API を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dcc85-119">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="dcc85-120">この設定は、<xref:System.Net.Http.HttpClient> や [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)) などの高レベル ネットワーク API で使用される HTTP プロトコル スタックにも影響します。</span><span class="sxs-lookup"><span data-stu-id="dcc85-120">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="dcc85-121">この設定を省略した場合、<xref:System.Net.Http.HttpClientHandler> では <xref:System.Net.Http.SocketsHttpHandler> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dcc85-121">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="dcc85-122">これは、値を `true` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="dcc85-122">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="dcc85-123">この設定は、<xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> メソッドを呼び出すことによりプログラムで構成できます。</span><span class="sxs-lookup"><span data-stu-id="dcc85-123">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="dcc85-124">設定の名前</span><span class="sxs-lookup"><span data-stu-id="dcc85-124">Setting name</span></span> | <span data-ttu-id="dcc85-125">値</span><span class="sxs-lookup"><span data-stu-id="dcc85-125">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dcc85-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="dcc85-126">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="dcc85-127">`true` - <xref:System.Net.Http.SocketsHttpHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="dcc85-127">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="dcc85-128">`false` - Windows では <xref:System.Net.Http.WinHttpHandler>、Linux では [libcurl](https://curl.haxx.se/libcurl/) の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="dcc85-128">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="dcc85-129">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="dcc85-129">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="dcc85-130">`1` - <xref:System.Net.Http.SocketsHttpHandler> の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="dcc85-130">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="dcc85-131">`0` - Windows では <xref:System.Net.Http.WinHttpHandler>、Linux では [libcurl](https://curl.haxx.se/libcurl/) の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="dcc85-131">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="dcc85-132">.NET 5 以降では、`System.Net.Http.UseSocketsHttpHandler` 設定は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dcc85-132">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
