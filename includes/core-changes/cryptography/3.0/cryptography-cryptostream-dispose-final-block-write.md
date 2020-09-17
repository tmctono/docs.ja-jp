---
ms.openlocfilehash: 7766a59131fffe2b436c15a5ff58e67001be7941
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065105"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a><span data-ttu-id="9fcf3-101">CryptoStream.Dispose は書き込み時にのみ最後のブロックを変換する</span><span class="sxs-lookup"><span data-stu-id="9fcf3-101">CryptoStream.Dispose transforms final block only when writing</span></span>

<span data-ttu-id="9fcf3-102">`CryptoStream` 操作を完了するために使用される <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> メソッドは、読み取り時に最後のブロックの変換を試行しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9fcf3-102">The <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> method, which is used to finish `CryptoStream` operations, no longer attempts to transform the final block when reading.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9fcf3-103">変更内容</span><span class="sxs-lookup"><span data-stu-id="9fcf3-103">Change description</span></span>

<span data-ttu-id="9fcf3-104">以前のバージョンの .NET では、ユーザーが <xref:System.Security.Cryptography.CryptoStreamMode.Read> モードで <xref:System.Security.Cryptography.CryptoStream> を使用するときに不完全な読み取りを実行した場合、<xref:System.Security.Cryptography.CryptoStream.Dispose%2A> メソッドから例外がスローされる可能性がありました (たとえば、パディングで AES を使用する場合)。</span><span class="sxs-lookup"><span data-stu-id="9fcf3-104">In previous .NET versions, if a user performed an incomplete read when using <xref:System.Security.Cryptography.CryptoStream> in <xref:System.Security.Cryptography.CryptoStreamMode.Read> mode, the <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> method could throw an exception (for example, when using AES with padding).</span></span> <span data-ttu-id="9fcf3-105">例外がスローされた理由は、最後のブロックの変換が試みられたがデータが不完全だったことにありました。</span><span class="sxs-lookup"><span data-stu-id="9fcf3-105">The exception was thrown because the final block was attempted to be transformed but the data was incomplete.</span></span>

<span data-ttu-id="9fcf3-106">.NET Core 3.0 以降のバージョンでは、<xref:System.Security.Cryptography.CryptoStream.Dispose%2A> が読み取り時に最後のブロックの変換を試行しなくなりました。これにより、不完全な読み取りが許容されます。</span><span class="sxs-lookup"><span data-stu-id="9fcf3-106">In .NET Core 3.0 and later versions, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> no longer tries to transform the final block when reading, which allows for incomplete reads.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9fcf3-107">変更理由</span><span class="sxs-lookup"><span data-stu-id="9fcf3-107">Reason for change</span></span>

<span data-ttu-id="9fcf3-108">この変更により、ネットワーク操作がキャンセルされたときに、例外をキャッチする必要なく、暗号化ストリームからの不完全な読み取りが可能になります。</span><span class="sxs-lookup"><span data-stu-id="9fcf3-108">This change enables incomplete reads from the crypto stream when a network operation is cancelled, without the need to catch an exception.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9fcf3-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9fcf3-109">Version introduced</span></span>

<span data-ttu-id="9fcf3-110">3.0</span><span class="sxs-lookup"><span data-stu-id="9fcf3-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9fcf3-111">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="9fcf3-111">Recommended action</span></span>

<span data-ttu-id="9fcf3-112">ほとんどのアプリは、この変更の影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="9fcf3-112">Most apps should not be affected by this change.</span></span>

<span data-ttu-id="9fcf3-113">不完全な読み取りが発生した場合にアプリケーションが例外をキャッチしても、その `catch` ブロックを削除できます。</span><span class="sxs-lookup"><span data-stu-id="9fcf3-113">If your application previously caught an exception in case of an incomplete read, you can delete that `catch` block.</span></span>
<span data-ttu-id="9fcf3-114">ご利用のアプリがハッシュ シナリオで最後のブロックの変換を使用した場合、ストリーム全体が破棄される前にそれを確実に読み取るようにする必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9fcf3-114">If your app used transforming of the final block in hashing scenarios, you might need to ensure that the entire stream is read before it's disposed.</span></span>

#### <a name="category"></a><span data-ttu-id="9fcf3-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="9fcf3-115">Category</span></span>

<span data-ttu-id="9fcf3-116">暗号</span><span class="sxs-lookup"><span data-stu-id="9fcf3-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9fcf3-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="9fcf3-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
