---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235535"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a><span data-ttu-id="43575-101">sql_variant データはデータベースの照合順序ではなく、sql_variant の照合順序を使用する</span><span class="sxs-lookup"><span data-stu-id="43575-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="43575-102">説明</span><span class="sxs-lookup"><span data-stu-id="43575-102">Details</span></span>|<span data-ttu-id="43575-103"><code>sql_variant</code> データはデータベースの照合順序ではなく <code>sql_variant</code> の照合順序を使用します。</span><span class="sxs-lookup"><span data-stu-id="43575-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>|
|<span data-ttu-id="43575-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="43575-104">Suggestion</span></span>|<span data-ttu-id="43575-105">この変更により、データベースの照合順序が <code>sql_variant</code> の照合順序と異なる場合にデータ破損が生じる可能性に対応できます。</span><span class="sxs-lookup"><span data-stu-id="43575-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="43575-106">破損したデータに依存するアプリケーションでは、エラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="43575-106">Applications that rely on the corrupted data may experience failure.</span></span>|
|<span data-ttu-id="43575-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="43575-107">Scope</span></span>|<span data-ttu-id="43575-108">透明</span><span class="sxs-lookup"><span data-stu-id="43575-108">Transparent</span></span>|
|<span data-ttu-id="43575-109">Version</span><span class="sxs-lookup"><span data-stu-id="43575-109">Version</span></span>|<span data-ttu-id="43575-110">4.5</span><span class="sxs-lookup"><span data-stu-id="43575-110">4.5</span></span>|
|<span data-ttu-id="43575-111">型</span><span class="sxs-lookup"><span data-stu-id="43575-111">Type</span></span>|<span data-ttu-id="43575-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="43575-112">Runtime</span></span>|
