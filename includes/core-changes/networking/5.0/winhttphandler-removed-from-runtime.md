---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608479"
---
### <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="8c8cd-101">.NET ランタイムからの WinHttpHandler の削除</span><span class="sxs-lookup"><span data-stu-id="8c8cd-101">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="8c8cd-102">`WinHttpHandler` クラスが *System.Net.Http.dll* アセンブリから削除されました。</span><span class="sxs-lookup"><span data-stu-id="8c8cd-102">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="8c8cd-103">現在、これは帯域外 (OOB) [NuGet パッケージ](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)としてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c8cd-103">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8c8cd-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="8c8cd-104">Version introduced</span></span>

<span data-ttu-id="8c8cd-105">5.0</span><span class="sxs-lookup"><span data-stu-id="8c8cd-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="8c8cd-106">変更の説明</span><span class="sxs-lookup"><span data-stu-id="8c8cd-106">Change description</span></span>

<span data-ttu-id="8c8cd-107">以前のバージョンの .NET では、<xref:System.Net.Http.WinHttpHandler> クラスは .NET のコア ライブラリの一部として使用できました。</span><span class="sxs-lookup"><span data-stu-id="8c8cd-107">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="8c8cd-108">.NET 5.0 以降、<xref:System.Net.Http.WinHttpHandler> クラスは、別にインストールする [NuGet パッケージ](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)のみとして用意されています。</span><span class="sxs-lookup"><span data-stu-id="8c8cd-108">Starting in .NET 5.0, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8c8cd-109">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="8c8cd-109">Recommended action</span></span>

<span data-ttu-id="8c8cd-110">[System.Net.Http.WinHttpHandler NuGet パッケージ](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c8cd-110">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="8c8cd-111">または、WinHTTP 固有の機能を必要としない場合は、代わりに <xref:System.Net.Http.SocketsHttpHandler> を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c8cd-111">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

#### <a name="category"></a><span data-ttu-id="8c8cd-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="8c8cd-112">Category</span></span>

<span data-ttu-id="8c8cd-113">ネットワーキング</span><span class="sxs-lookup"><span data-stu-id="8c8cd-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8c8cd-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="8c8cd-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
