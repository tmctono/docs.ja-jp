---
ms.openlocfilehash: ff156afb3da4b921517fd841c5de2295265a8d7b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198476"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a><span data-ttu-id="ad8a1-101">HttpRequestMessage.Version の既定値が 1.1 に変更された</span><span class="sxs-lookup"><span data-stu-id="ad8a1-101">Default value of HttpRequestMessage.Version changed to 1.1</span></span>

<span data-ttu-id="ad8a1-102"><xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> プロパティの既定値が 2.0 から 1.1 に変更されました。</span><span class="sxs-lookup"><span data-stu-id="ad8a1-102">The default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property has changed from 2.0 to 1.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ad8a1-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="ad8a1-103">Version introduced</span></span>

<span data-ttu-id="ad8a1-104">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ad8a1-104">.NET Core 3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="ad8a1-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="ad8a1-105">Change description</span></span>

<span data-ttu-id="ad8a1-106">.NET Core 1.0 から 2.0 では、<xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> プロパティの既定値は 1.1 です。</span><span class="sxs-lookup"><span data-stu-id="ad8a1-106">In .NET Core 1.0 through 2.0, the default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is 1.1.</span></span> <span data-ttu-id="ad8a1-107">.NET Core 2.1 以降では、2.1 に変更されました。</span><span class="sxs-lookup"><span data-stu-id="ad8a1-107">Starting with .NET Core 2.1, it was changed to 2.1.</span></span>

<span data-ttu-id="ad8a1-108">.NET Core 3.0 以降では、<xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> プロパティによって返される既定のバージョン番号は再び 1.1 になりました。</span><span class="sxs-lookup"><span data-stu-id="ad8a1-108">Starting with .NET Core 3.0, the default version number returned by the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is once again 1.1.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ad8a1-109">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="ad8a1-109">Recommended action</span></span>

<span data-ttu-id="ad8a1-110">既定値 2.0 を返す <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> プロパティに依存している場合は、コードを更新します。</span><span class="sxs-lookup"><span data-stu-id="ad8a1-110">Update your code if it depends on the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property returning a default value of 2.0.</span></span>

#### <a name="category"></a><span data-ttu-id="ad8a1-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="ad8a1-111">Category</span></span>

<span data-ttu-id="ad8a1-112">ネットワーキング</span><span class="sxs-lookup"><span data-stu-id="ad8a1-112">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ad8a1-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ad8a1-113">Affected APIs</span></span>

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-- >

