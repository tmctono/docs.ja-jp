---
ms.openlocfilehash: 9e98d3bca645cf82bf4fe99160dd096b0e274ef7
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802471"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="2cd69-101">Workflow SQL の永続化で主キー クラスターが追加され、一部の列の null 値が許可されない</span><span class="sxs-lookup"><span data-stu-id="2cd69-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2cd69-102">説明</span><span class="sxs-lookup"><span data-stu-id="2cd69-102">Details</span></span>|<span data-ttu-id="2cd69-103">.NET Framework 4.7 以降では、SqlWorkflowInstanceStoreSchema.sql スクリプトで SQL Workflow Instance Store (SWIS) に作成されたテーブルにはクラスター化された主キーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2cd69-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="2cd69-104">そのため、ID では <code>null</code> 値はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2cd69-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="2cd69-105">SWIS の操作には、この変更による影響はありません。</span><span class="sxs-lookup"><span data-stu-id="2cd69-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="2cd69-106">SQL Server トランザクション レプリケーションをサポートするように更新されました。</span><span class="sxs-lookup"><span data-stu-id="2cd69-106">The updates were made to support SQL Server Transactional Replication.</span></span>|
|<span data-ttu-id="2cd69-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2cd69-107">Suggestion</span></span>|<span data-ttu-id="2cd69-108">この変更では、SQL ファイルの SqlWorkflowInstanceStoreSchemaUpgrade.sql を既存のインストールに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cd69-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="2cd69-109">新しいデータベースのインストールは自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="2cd69-109">New database installations will automatically have the change.</span></span>|
|<span data-ttu-id="2cd69-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="2cd69-110">Scope</span></span>|<span data-ttu-id="2cd69-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="2cd69-111">Edge</span></span>|
|<span data-ttu-id="2cd69-112">Version</span><span class="sxs-lookup"><span data-stu-id="2cd69-112">Version</span></span>|<span data-ttu-id="2cd69-113">4.7</span><span class="sxs-lookup"><span data-stu-id="2cd69-113">4.7</span></span>|
|<span data-ttu-id="2cd69-114">型</span><span class="sxs-lookup"><span data-stu-id="2cd69-114">Type</span></span>|<span data-ttu-id="2cd69-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2cd69-115">Runtime</span></span>|

