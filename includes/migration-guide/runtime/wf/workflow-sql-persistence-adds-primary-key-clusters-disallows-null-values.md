---
ms.openlocfilehash: 566a3e0455b30e901b09be88b4256ffe67bdc2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802471"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="eae80-101">Workflow SQL の永続化で主キー クラスターが追加され、一部の列の null 値が許可されない</span><span class="sxs-lookup"><span data-stu-id="eae80-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

|   |   |
|---|---|
|<span data-ttu-id="eae80-102">説明</span><span class="sxs-lookup"><span data-stu-id="eae80-102">Details</span></span>|<span data-ttu-id="eae80-103">.NET Framework 4.7 以降では、SqlWorkflowInstanceStoreSchema.sql スクリプトで SQL Workflow Instance Store (SWIS) に作成されたテーブルにはクラスター化された主キーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="eae80-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="eae80-104">そのため、ID では <code>null</code> 値はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="eae80-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="eae80-105">SWIS の操作には、この変更による影響はありません。</span><span class="sxs-lookup"><span data-stu-id="eae80-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="eae80-106">SQL Server トランザクション レプリケーションをサポートするように更新されました。</span><span class="sxs-lookup"><span data-stu-id="eae80-106">The updates were made to support SQL Server Transactional Replication.</span></span>|
|<span data-ttu-id="eae80-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="eae80-107">Suggestion</span></span>|<span data-ttu-id="eae80-108">この変更では、SQL ファイルの SqlWorkflowInstanceStoreSchemaUpgrade.sql を既存のインストールに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae80-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="eae80-109">新しいデータベースのインストールは自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="eae80-109">New database installations will automatically have the change.</span></span>|
|<span data-ttu-id="eae80-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="eae80-110">Scope</span></span>|<span data-ttu-id="eae80-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="eae80-111">Edge</span></span>|
|<span data-ttu-id="eae80-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="eae80-112">Version</span></span>|<span data-ttu-id="eae80-113">4.7</span><span class="sxs-lookup"><span data-stu-id="eae80-113">4.7</span></span>|
|<span data-ttu-id="eae80-114">[種類]</span><span class="sxs-lookup"><span data-stu-id="eae80-114">Type</span></span>|<span data-ttu-id="eae80-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="eae80-115">Runtime</span></span>|
