---
ms.openlocfilehash: af10716fe5f4c07091e8605cdf620e4a499fb1e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620180"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="7bfae-101">iPad はブラウザー機能になったため、カスタム機能ファイルでは使用できない</span><span class="sxs-lookup"><span data-stu-id="7bfae-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

#### <a name="details"></a><span data-ttu-id="7bfae-102">説明</span><span class="sxs-lookup"><span data-stu-id="7bfae-102">Details</span></span>

<span data-ttu-id="7bfae-103">.NET Framework 4.5 以降では、iPad は既定の ASP.NET ブラウザー機能ファイルの識別子であるため、カスタム機能ファイルでは使用できません</span><span class="sxs-lookup"><span data-stu-id="7bfae-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7bfae-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7bfae-104">Suggestion</span></span>

<span data-ttu-id="7bfae-105">iPad 固有の機能が必要な場合は、ユーザー エージェントのマッチングで新しい &quot;IPad&quot; ID を生成するのではなく、定義済みのゲートウェイ refID &quot;IPad&quot; で機能を設定して、iPad の動作を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bfae-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>

| <span data-ttu-id="7bfae-106">名前</span><span class="sxs-lookup"><span data-stu-id="7bfae-106">Name</span></span>    | <span data-ttu-id="7bfae-107">[値]</span><span class="sxs-lookup"><span data-stu-id="7bfae-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7bfae-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="7bfae-108">Scope</span></span>   |<span data-ttu-id="7bfae-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="7bfae-109">Edge</span></span>|
|<span data-ttu-id="7bfae-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="7bfae-110">Version</span></span>|<span data-ttu-id="7bfae-111">4.5</span><span class="sxs-lookup"><span data-stu-id="7bfae-111">4.5</span></span>|
|<span data-ttu-id="7bfae-112">種類</span><span class="sxs-lookup"><span data-stu-id="7bfae-112">Type</span></span>|<span data-ttu-id="7bfae-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="7bfae-113">Runtime</span></span>|
