---
ms.openlocfilehash: 88a0b7e04c7015ca3fa5abd8a6897dafcbe41c49
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557967"
---
### <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="809e5-101">MulticastOption.Group で null 値を受け付けない</span><span class="sxs-lookup"><span data-stu-id="809e5-101">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="809e5-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> で `null` の値を受け付けなくなりました。</span><span class="sxs-lookup"><span data-stu-id="809e5-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="809e5-103">プロパティを `null` に設定すると、<xref:System.ArgumentNullException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="809e5-103">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="809e5-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="809e5-104">Version introduced</span></span>

<span data-ttu-id="809e5-105">5.0</span><span class="sxs-lookup"><span data-stu-id="809e5-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="809e5-106">変更の説明</span><span class="sxs-lookup"><span data-stu-id="809e5-106">Change description</span></span>

<span data-ttu-id="809e5-107">以前のバージョンの .NET では、<xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> プロパティを `null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="809e5-107">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="809e5-108"><xref:System.Net.Sockets.MulticastOption> が後で <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> に渡される場合、ランタイムによって <xref:System.NullReferenceException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="809e5-108">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="809e5-109">.NET 5.0 以降では、プロパティを `null` に設定した場合、<xref:System.ArgumentNullException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="809e5-109">In .NET 5.0 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="809e5-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="809e5-110">Reason for change</span></span>

<span data-ttu-id="809e5-111">Framework デザイン ガイドラインとの一貫性を保つため、値が `null` の場合に <xref:System.ArgumentNullException> をスローするようにプロパティは更新されました。</span><span class="sxs-lookup"><span data-stu-id="809e5-111">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="809e5-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="809e5-112">Recommended action</span></span>

<span data-ttu-id="809e5-113"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> に `null` を設定していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="809e5-113">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

#### <a name="category"></a><span data-ttu-id="809e5-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="809e5-114">Category</span></span>

<span data-ttu-id="809e5-115">ネットワーキング</span><span class="sxs-lookup"><span data-stu-id="809e5-115">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="809e5-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="809e5-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

-->
