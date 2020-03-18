---
ms.openlocfilehash: e7154919d6a09a04e650d5546feb2ae6c6cc912f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859179"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="b55e7-101">HttpRuntime.AppDomainAppPath で NullReferenceException がスローされる</span><span class="sxs-lookup"><span data-stu-id="b55e7-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b55e7-102">説明</span><span class="sxs-lookup"><span data-stu-id="b55e7-102">Details</span></span>|<span data-ttu-id="b55e7-103">ランタイムによってスローされる、.NET Framework 4.6.2、<code>T:System.NullReferenceException</code>取得するときに、 <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> null 文字を含む値です。 .NET Framework 4.6.1 と以前のバージョンでは、ランタイムによってスローされる、<code>T:System.ArgumentNullException</code>です。</span><span class="sxs-lookup"><span data-stu-id="b55e7-103">In the .NET Framework 4.6.2, the runtime throws a <code>T:System.NullReferenceException</code> when retrieving a <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an <code>T:System.ArgumentNullException</code>.</span></span>|
|<span data-ttu-id="b55e7-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b55e7-104">Suggestion</span></span>|<span data-ttu-id="b55e7-105">次のいずれかでこの変更に対応できます。</span><span class="sxs-lookup"><span data-stu-id="b55e7-105">You can do either of the follow to respond to this change:</span></span><ul><li><span data-ttu-id="b55e7-106">アプリケーションが .NET Framework 4.6.2 で実行されている場合には <code>T:System.NullReferenceException</code> を処理します。</span><span class="sxs-lookup"><span data-stu-id="b55e7-106">Handle the <code>T:System.NullReferenceException</code> if you application is running on the .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="b55e7-107">.NET Framework 4.7 にアップグレードします。以前の動作が復元され、<code>T:System.ArgumentNullException</code> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="b55e7-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an <code>T:System.ArgumentNullException</code>.</span></span></li></ul>|
|<span data-ttu-id="b55e7-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="b55e7-108">Scope</span></span>|<span data-ttu-id="b55e7-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="b55e7-109">Edge</span></span>|
|<span data-ttu-id="b55e7-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="b55e7-110">Version</span></span>|<span data-ttu-id="b55e7-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="b55e7-111">4.6.2</span></span>|
|<span data-ttu-id="b55e7-112">[種類]</span><span class="sxs-lookup"><span data-stu-id="b55e7-112">Type</span></span>|<span data-ttu-id="b55e7-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="b55e7-113">Retargeting</span></span>|
|<span data-ttu-id="b55e7-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b55e7-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|
