---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617538"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="c2355-101">HttpRuntime.AppDomainAppPath で NullReferenceException がスローされる</span><span class="sxs-lookup"><span data-stu-id="c2355-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="c2355-102">説明</span><span class="sxs-lookup"><span data-stu-id="c2355-102">Details</span></span>

<span data-ttu-id="c2355-103">ランタイムによってスローされる、.NET Framework 4.6.2、`T:System.NullReferenceException`取得するときに、 `P:System.Web.HttpRuntime.AppDomainAppPath` null 文字を含む値です。 .NET Framework 4.6.1 と以前のバージョンでは、ランタイムによってスローされる、`T:System.ArgumentNullException`です。</span><span class="sxs-lookup"><span data-stu-id="c2355-103">In the .NET Framework 4.6.2, the runtime throws a `T:System.NullReferenceException` when retrieving a `P:System.Web.HttpRuntime.AppDomainAppPath` value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an `T:System.ArgumentNullException`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c2355-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c2355-104">Suggestion</span></span>

<span data-ttu-id="c2355-105">次のいずれかでこの変更に対応できます。</span><span class="sxs-lookup"><span data-stu-id="c2355-105">You can do either of the follow to respond to this change:</span></span>

- <span data-ttu-id="c2355-106">アプリケーションが .NET Framework 4.6.2 で実行されている場合には `T:System.NullReferenceException` を処理します。</span><span class="sxs-lookup"><span data-stu-id="c2355-106">Handle the `T:System.NullReferenceException` if you application is running on the .NET Framework 4.6.2.</span></span>
- <span data-ttu-id="c2355-107">.NET Framework 4.7 にアップグレードします。以前の動作が復元され、`T:System.ArgumentNullException` がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c2355-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an `T:System.ArgumentNullException`.</span></span>

| <span data-ttu-id="c2355-108">名前</span><span class="sxs-lookup"><span data-stu-id="c2355-108">Name</span></span>    | <span data-ttu-id="c2355-109">値</span><span class="sxs-lookup"><span data-stu-id="c2355-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c2355-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="c2355-110">Scope</span></span>   | <span data-ttu-id="c2355-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="c2355-111">Edge</span></span>        |
| <span data-ttu-id="c2355-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="c2355-112">Version</span></span> | <span data-ttu-id="c2355-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c2355-113">4.6.2</span></span>       |
| <span data-ttu-id="c2355-114">種類</span><span class="sxs-lookup"><span data-stu-id="c2355-114">Type</span></span>    | <span data-ttu-id="c2355-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="c2355-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c2355-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c2355-116">Affected APIs</span></span>

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>
