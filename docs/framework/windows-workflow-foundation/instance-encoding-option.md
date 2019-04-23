---
title: インスタンス エンコーディング オプション
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: c4de7c45d899f45a7b5b71d563257d9accb8fdbb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773845"
---
# <a name="instance-encoding-option"></a><span data-ttu-id="be28c-102">インスタンス エンコーディング オプション</span><span class="sxs-lookup"><span data-stu-id="be28c-102">Instance Encoding Option</span></span>
<span data-ttu-id="be28c-103">**インスタンス エンコーディング オプション**SQL Workflow Instance Store のプロパティでは、SQL 永続化プロバイダーが保存する前に、GZip アルゴリズムを使用して、ワークフロー インスタンス状態情報を圧縮するかどうかを指定できます、。永続性データベースに情報。</span><span class="sxs-lookup"><span data-stu-id="be28c-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="be28c-104">このプロパティに使用できる値は次のとおりです。GZip と None です。</span><span class="sxs-lookup"><span data-stu-id="be28c-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="be28c-105">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="be28c-105">The default value is None.</span></span> <span data-ttu-id="be28c-106">これらのオプションを次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="be28c-106">The following list describes these options.</span></span>  
  
1. <span data-ttu-id="be28c-107">**GZip**します。</span><span class="sxs-lookup"><span data-stu-id="be28c-107">**GZip**.</span></span> <span data-ttu-id="be28c-108">永続化プロバイダーは、永続性データベースに状態情報を永続化する前に、GZip アルゴリズムを使用して状態情報をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="be28c-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2. <span data-ttu-id="be28c-109">**None**します。</span><span class="sxs-lookup"><span data-stu-id="be28c-109">**None**.</span></span> <span data-ttu-id="be28c-110">永続化プロバイダーは、永続性データベースに情報を保存する前は、状態情報をエンコードしません。</span><span class="sxs-lookup"><span data-stu-id="be28c-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="be28c-111">GZip を使用してワークフロー インスタンスの状態情報をエンコードすると、SQL データベースのメモリ消費量が減ります。また、ワークフロー サービス ホストが実行されているコンピューターとは異なるコンピューターがネットワーク上にあり、そこにデータベースが配置されている場合、ネットワークの消費量も減ります。</span><span class="sxs-lookup"><span data-stu-id="be28c-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="be28c-112">一般的なガイダンスを設定するのには、**インスタンス エンコーディング オプション**プロパティを**None**ワークフロー インスタンスの状態が小さい場合。</span><span class="sxs-lookup"><span data-stu-id="be28c-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
