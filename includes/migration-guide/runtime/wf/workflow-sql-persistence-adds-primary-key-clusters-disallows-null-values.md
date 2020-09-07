---
ms.openlocfilehash: cb9305f623044233082286863d2f2d2c7e9d665a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497221"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="86694-101">Workflow SQL の永続化で主キー クラスターが追加され、一部の列の null 値が許可されない</span><span class="sxs-lookup"><span data-stu-id="86694-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

#### <a name="details"></a><span data-ttu-id="86694-102">説明</span><span class="sxs-lookup"><span data-stu-id="86694-102">Details</span></span>

<span data-ttu-id="86694-103">.NET Framework 4.7 以降では、SqlWorkflowInstanceStoreSchema.sql スクリプトで SQL Workflow Instance Store (SWIS) に作成されたテーブルにはクラスター化された主キーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="86694-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="86694-104">そのため、ID では <code>null</code> 値はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="86694-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="86694-105">SWIS の操作には、この変更による影響はありません。</span><span class="sxs-lookup"><span data-stu-id="86694-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="86694-106">SQL Server トランザクション レプリケーションをサポートするように更新されました。</span><span class="sxs-lookup"><span data-stu-id="86694-106">The updates were made to support SQL Server Transactional Replication.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="86694-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="86694-107">Suggestion</span></span>

<span data-ttu-id="86694-108">この変更では、SQL ファイルの SqlWorkflowInstanceStoreSchemaUpgrade.sql を既存のインストールに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86694-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="86694-109">新しいデータベースのインストールは自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="86694-109">New database installations will automatically have the change.</span></span>

| <span data-ttu-id="86694-110">名前</span><span class="sxs-lookup"><span data-stu-id="86694-110">Name</span></span>    | <span data-ttu-id="86694-111">値</span><span class="sxs-lookup"><span data-stu-id="86694-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="86694-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="86694-112">Scope</span></span>   |<span data-ttu-id="86694-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="86694-113">Edge</span></span>|
|<span data-ttu-id="86694-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="86694-114">Version</span></span>|<span data-ttu-id="86694-115">4.7</span><span class="sxs-lookup"><span data-stu-id="86694-115">4.7</span></span>|
|<span data-ttu-id="86694-116">種類</span><span class="sxs-lookup"><span data-stu-id="86694-116">Type</span></span>|<span data-ttu-id="86694-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="86694-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="86694-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="86694-118">Affected APIs</span></span>

<span data-ttu-id="86694-119">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="86694-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
