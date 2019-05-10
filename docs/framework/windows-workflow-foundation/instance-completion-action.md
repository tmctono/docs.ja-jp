---
title: インスタンス完了アクション
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: d68f41a586e44f96c9ca26cf8a142a2782adaa36
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662977"
---
# <a name="instance-completion-action"></a><span data-ttu-id="3dc8a-102">インスタンス完了アクション</span><span class="sxs-lookup"><span data-stu-id="3dc8a-102">Instance Completion Action</span></span>
<span data-ttu-id="3dc8a-103">**インスタンス完了アクション**SQL Workflow Instance Store のプロパティを使用して、削除かどうか、データとワークフロー インスタンスのメタデータは永続性データベースからインスタンスの完了後を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3dc8a-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="3dc8a-104">このプロパティの使用できる値は**DeleteAll**と**DeleteNothing**します。</span><span class="sxs-lookup"><span data-stu-id="3dc8a-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="3dc8a-105">これらのオプションについて次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="3dc8a-105">The following list describes these options:</span></span>  
  
- <span data-ttu-id="3dc8a-106">**DeleteAll (既定値)。**</span><span class="sxs-lookup"><span data-stu-id="3dc8a-106">**DeleteAll (default).**</span></span> <span data-ttu-id="3dc8a-107">このプロパティの値を DeleteAll に設定すると、ワークフロー インスタンスの完了後に、永続性データベースからワークフロー インスタンスのデータおよびメタデータは削除されます。</span><span class="sxs-lookup"><span data-stu-id="3dc8a-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>  
  
- <span data-ttu-id="3dc8a-108">**DeleteNothing します。**</span><span class="sxs-lookup"><span data-stu-id="3dc8a-108">**DeleteNothing.**</span></span> <span data-ttu-id="3dc8a-109">このプロパティの値を DeleteNothing に設定すると、ワークフロー インスタンスが完了しても、ワークフロー インスタンスのデータおよびメタデータは永続性データベースに残ります。</span><span class="sxs-lookup"><span data-stu-id="3dc8a-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="3dc8a-110">インスタンスの完了後にインスタンス状態情報を残すと、永続性データベースのサイズが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="3dc8a-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="3dc8a-111">データベースのサイズが大きくなるにつれて、永続性サブシステムが実行するデータベース操作にかかる時間が長くなります。そのため、永続性データベースからインスタンス状態情報を定期的に削除して、パフォーマンスの要件を満たすレベルでサービスが実行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="3dc8a-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
