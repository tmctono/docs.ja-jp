---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620290"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="0940c-101">sql_variant データはデータベースの照合順序ではなく、sql_variant の照合順序を使用する</span><span class="sxs-lookup"><span data-stu-id="0940c-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="0940c-102">説明</span><span class="sxs-lookup"><span data-stu-id="0940c-102">Details</span></span>

<span data-ttu-id="0940c-103"><code>sql_variant</code> データはデータベースの照合順序ではなく <code>sql_variant</code> の照合順序を使用します。</span><span class="sxs-lookup"><span data-stu-id="0940c-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0940c-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0940c-104">Suggestion</span></span>

<span data-ttu-id="0940c-105">この変更により、データベースの照合順序が <code>sql_variant</code> の照合順序と異なる場合にデータ破損が生じる可能性に対応できます。</span><span class="sxs-lookup"><span data-stu-id="0940c-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="0940c-106">破損したデータに依存するアプリケーションでは、エラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0940c-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="0940c-107">名前</span><span class="sxs-lookup"><span data-stu-id="0940c-107">Name</span></span>    | <span data-ttu-id="0940c-108">[値]</span><span class="sxs-lookup"><span data-stu-id="0940c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0940c-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="0940c-109">Scope</span></span>   |<span data-ttu-id="0940c-110">透明</span><span class="sxs-lookup"><span data-stu-id="0940c-110">Transparent</span></span>|
|<span data-ttu-id="0940c-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="0940c-111">Version</span></span>|<span data-ttu-id="0940c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0940c-112">4.5</span></span>|
|<span data-ttu-id="0940c-113">種類</span><span class="sxs-lookup"><span data-stu-id="0940c-113">Type</span></span>|<span data-ttu-id="0940c-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="0940c-114">Runtime</span></span>|
