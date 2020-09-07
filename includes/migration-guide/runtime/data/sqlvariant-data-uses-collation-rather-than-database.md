---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497470"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="d1505-101">sql_variant データはデータベースの照合順序ではなく、sql_variant の照合順序を使用する</span><span class="sxs-lookup"><span data-stu-id="d1505-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="d1505-102">説明</span><span class="sxs-lookup"><span data-stu-id="d1505-102">Details</span></span>

<span data-ttu-id="d1505-103"><code>sql_variant</code> データはデータベースの照合順序ではなく <code>sql_variant</code> の照合順序を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1505-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d1505-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d1505-104">Suggestion</span></span>

<span data-ttu-id="d1505-105">この変更により、データベースの照合順序が <code>sql_variant</code> の照合順序と異なる場合にデータ破損が生じる可能性に対応できます。</span><span class="sxs-lookup"><span data-stu-id="d1505-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="d1505-106">破損したデータに依存するアプリケーションでは、エラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1505-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="d1505-107">名前</span><span class="sxs-lookup"><span data-stu-id="d1505-107">Name</span></span>    | <span data-ttu-id="d1505-108">[値]</span><span class="sxs-lookup"><span data-stu-id="d1505-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d1505-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="d1505-109">Scope</span></span>   |<span data-ttu-id="d1505-110">透明</span><span class="sxs-lookup"><span data-stu-id="d1505-110">Transparent</span></span>|
|<span data-ttu-id="d1505-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="d1505-111">Version</span></span>|<span data-ttu-id="d1505-112">4.5</span><span class="sxs-lookup"><span data-stu-id="d1505-112">4.5</span></span>|
|<span data-ttu-id="d1505-113">種類</span><span class="sxs-lookup"><span data-stu-id="d1505-113">Type</span></span>|<span data-ttu-id="d1505-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d1505-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d1505-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d1505-115">Affected APIs</span></span>

<span data-ttu-id="d1505-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="d1505-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
