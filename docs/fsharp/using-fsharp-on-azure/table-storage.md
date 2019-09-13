---
title: F# を使用した Azure Table Storage の概要
description: Azure Table storage または Azure Cosmos DB を使用して、構造化データをクラウドに格納します。
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: f5fe2fe667b6d529bba4d29729a975c7890b5aba
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929004"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="e00b7-103">F を使用して Azure Table storage と Azure Cosmos DB Table API を開始する\#</span><span class="sxs-lookup"><span data-stu-id="e00b7-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F\#</span></span>

<span data-ttu-id="e00b7-104">Azure Table storage は、構造化された NoSQL データをクラウドに格納するサービスです。</span><span class="sxs-lookup"><span data-stu-id="e00b7-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="e00b7-105">Table storage は、スキーマなしの設計によるキー/属性ストアです。</span><span class="sxs-lookup"><span data-stu-id="e00b7-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="e00b7-106">テーブルストレージはスキーマ aless であるため、アプリケーションのニーズの進化に合わせてデータを簡単に調整できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="e00b7-107">データへのアクセスは、あらゆる種類のアプリケーションで高速かつコスト効率の高い方法で実現できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="e00b7-108">通常、テーブルストレージは、類似したデータ量に対して従来の SQL よりも大幅に低コストになります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="e00b7-109">Table storage を使用すると、web アプリケーションのユーザーデータ、アドレス帳、デバイス情報、およびサービスに必要なその他の種類のメタデータなど、柔軟なデータセットを格納できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="e00b7-110">テーブルには任意の数のエンティティを格納できます。ストレージアカウントには、ストレージアカウントの容量制限まで、任意の数のテーブルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="e00b7-111">Azure Cosmos DB は、Azure Table storage 用に作成されたアプリケーションの Table API を提供し、次のような premium 機能を必要とします。</span><span class="sxs-lookup"><span data-stu-id="e00b7-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="e00b7-112">ターンキーグローバル配信。</span><span class="sxs-lookup"><span data-stu-id="e00b7-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="e00b7-113">全世界の専用スループット。</span><span class="sxs-lookup"><span data-stu-id="e00b7-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="e00b7-114">99パーセンタイルでの1桁のミリ秒待機時間。</span><span class="sxs-lookup"><span data-stu-id="e00b7-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="e00b7-115">高可用性が保証されます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="e00b7-116">自動セカンダリインデックス作成。</span><span class="sxs-lookup"><span data-stu-id="e00b7-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="e00b7-117">Azure Table storage 用に作成されたアプリケーションは、コードを変更せずに Table API を使用して Azure Cosmos DB に移行し、premium 機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="e00b7-118">Table API には、.NET、Java、Python、および node.js で使用できるクライアント Sdk があります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="e00b7-119">詳細については、「 [Azure Cosmos DB Table API の概要](https://docs.microsoft.com/azure/cosmos-db/table-introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e00b7-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="e00b7-120">このチュートリアルについて</span><span class="sxs-lookup"><span data-stu-id="e00b7-120">About this tutorial</span></span>

<span data-ttu-id="e00b7-121">このチュートリアルでは、Azure Table storage またはなど、Azure Cosmos DB テーブル API、作成しテーブルの削除し挿入、更新、削除、およびテーブル データのクエリを使用していくつかの一般的なタスクを実行する F# コードを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e00b7-122">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e00b7-122">Prerequisites</span></span>

<span data-ttu-id="e00b7-123">このガイドを使用するには、最初に[Azure ストレージアカウント](/azure/storage/storage-create-storage-account)または[Azure Cosmos DB アカウント](https://azure.microsoft.com/try/cosmosdb/)を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="e00b7-124">作成して、F# スクリプトと開始 F# 対話型</span><span class="sxs-lookup"><span data-stu-id="e00b7-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="e00b7-125">この記事のサンプルは、F# アプリケーションまたは F# スクリプトのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="e00b7-126">F# スクリプトを作成するには、ファイルを作成、`.fsx`拡張機能の例では、 `tables.fsx`、F# 開発環境にします。</span><span class="sxs-lookup"><span data-stu-id="e00b7-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="e00b7-127">次に、[パケット](https://fsprojects.github.io/Paket/)や`WindowsAzure.Storage` [NuGet](https://www.nuget.org/)などの[パッケージマネージャー](package-management.md)を使用して、 `#r`ディレクティブを`WindowsAzure.Storage.dll`使用してスクリプトにパッケージと参照をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e00b7-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="e00b7-128">Microsoft Azure 名前空間`Microsoft.WindowsAzure.ConfigurationManager`を取得するために、に対してもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="e00b7-129">名前空間宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e00b7-129">Add namespace declarations</span></span>

<span data-ttu-id="e00b7-130">ファイルの先頭`open`に次のステートメントを追加します。 `tables.fsx`</span><span class="sxs-lookup"><span data-stu-id="e00b7-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="e00b7-131">Azure Storage 接続文字列を取得する</span><span class="sxs-lookup"><span data-stu-id="e00b7-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="e00b7-132">Azure Storage Table service に接続している場合は、このチュートリアルで使用する接続文字列が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="e00b7-133">Azure portal から接続文字列をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="e00b7-134">接続文字列の詳細については、「[ストレージ接続文字列の構成](/azure/storage/storage-configure-connection-string)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e00b7-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="e00b7-135">Azure Cosmos DB 接続文字列を取得する</span><span class="sxs-lookup"><span data-stu-id="e00b7-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="e00b7-136">Azure Cosmos DB に接続している場合は、このチュートリアルで使用する接続文字列が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="e00b7-137">Azure portal から接続文字列をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="e00b7-138">Azure portal の Cosmos DB アカウントで、[**設定** > ] **[接続文字列]** の順にクリックし、 **[コピー]** ボタンをクリックしてプライマリ接続文字列をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e00b7-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="e00b7-139">このチュートリアルでは、次の例のように、スクリプトに接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="e00b7-140">ただし、実際のプロジェクトではこの方法は**お勧めできません**。</span><span class="sxs-lookup"><span data-stu-id="e00b7-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="e00b7-141">ストレージアカウントキーは、ストレージアカウントのルートパスワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="e00b7-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="e00b7-142">ストレージアカウントキーは常に慎重に保護してください。</span><span class="sxs-lookup"><span data-stu-id="e00b7-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="e00b7-143">他のユーザーに配布したり、ハードコーディングしたり、他のユーザーがアクセスできるプレーンテキストファイルに保存したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="e00b7-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="e00b7-144">侵害された可能性があると思われる場合は、Azure ポータルを使用してキーを再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="e00b7-145">実際のアプリケーションでは、ストレージ接続文字列を維持する最善の方法は構成ファイルにあります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="e00b7-146">構成ファイルから接続文字列を取得するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="e00b7-147">Azure Configuration Manager の使用は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e00b7-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="e00b7-148">.NET Framework の`ConfigurationManager`型などの API を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="e00b7-149">接続文字列を解析する</span><span class="sxs-lookup"><span data-stu-id="e00b7-149">Parse the connection string</span></span>

<span data-ttu-id="e00b7-150">接続文字列を解析するには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="e00b7-151">これにより`CloudStorageAccount`、が返されます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="e00b7-152">Table service クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="e00b7-152">Create the Table service client</span></span>

<span data-ttu-id="e00b7-153">`CloudTableClient`クラスを使用すると、テーブルストレージ内のテーブルとエンティティを取得できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="e00b7-154">サービスクライアントを作成する方法の1つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="e00b7-155">これで、からデータを読み取り、テーブルストレージにデータを書き込むコードを記述する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="e00b7-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="e00b7-156">テーブルの作成</span><span class="sxs-lookup"><span data-stu-id="e00b7-156">Create a table</span></span>

<span data-ttu-id="e00b7-157">この例では、テーブルがまだ存在しない場合に作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="e00b7-158">エンティティをテーブルに追加する</span><span class="sxs-lookup"><span data-stu-id="e00b7-158">Add an entity to a table</span></span>

<span data-ttu-id="e00b7-159">エンティティは、から`TableEntity`継承される型を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="e00b7-160">は任意の`TableEntity`方法で拡張できますが、型にはパラメーターのないコンストラクターが*必要*です。</span><span class="sxs-lookup"><span data-stu-id="e00b7-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="e00b7-161">`get` と`set`の両方を持つプロパティのみが Azure テーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="e00b7-162">エンティティのパーティションキーと行キーは、テーブル内のエンティティを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="e00b7-163">同じパーティションキーを持つエンティティは、異なるパーティションキーを持つエンティティよりも迅速に照会できますが、多様なパーティションキーを使用すると、並列操作のスケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="e00b7-164">をパーティションキー `Customer` `lastName` として使用し、を行キーとして使用するの例を次`firstName`に示します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="e00b7-165">次に`Customer` 、テーブルにを追加します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="e00b7-166">これを行うには、 `TableOperation`テーブルで実行するを作成します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="e00b7-167">この場合は、 `Insert`操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="e00b7-168">エンティティのバッチを挿入する</span><span class="sxs-lookup"><span data-stu-id="e00b7-168">Insert a batch of entities</span></span>

<span data-ttu-id="e00b7-169">1回の書き込み操作を使用して、エンティティのバッチをテーブルに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="e00b7-170">バッチ操作を使用すると、複数の操作を1回の実行にまとめることができますが、いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="e00b7-171">同じバッチ操作で、更新、削除、および挿入を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="e00b7-172">バッチ操作には、最大100のエンティティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="e00b7-173">バッチ操作内のすべてのエンティティは、同じパーティションキーを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="e00b7-174">バッチ操作でクエリを実行することはできますが、バッチ内の唯一の操作である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="e00b7-175">バッチ操作に2つの挿入を結合するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="e00b7-176">パーティション内のすべてのエンティティを取得する</span><span class="sxs-lookup"><span data-stu-id="e00b7-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="e00b7-177">テーブルに対してパーティション内のすべてのエンティティを照会する`TableQuery`には、オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="e00b7-178">ここでは、"Smith" がパーティションキーであるエンティティをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="e00b7-179">結果は次のように印刷されます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="e00b7-180">パーティション内のエンティティの範囲を取得する</span><span class="sxs-lookup"><span data-stu-id="e00b7-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="e00b7-181">パーティション内のすべてのエンティティに対してクエリを実行しない場合は、パーティションキーフィルターと行キーフィルターを組み合わせて範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="e00b7-182">ここでは、2つのフィルターを使用して、行キー (名) がアルファベットの "M" よりも前の文字で始まる "Smith" パーティション内のすべてのエンティティを取得します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="e00b7-183">結果は次のように印刷されます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="e00b7-184">1つのエンティティを取得する</span><span class="sxs-lookup"><span data-stu-id="e00b7-184">Retrieve a single entity</span></span>

<span data-ttu-id="e00b7-185">1つの特定のエンティティを取得するクエリを記述できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="e00b7-186">ここでは、を`TableOperation`使用して、"Ben Smith" という顧客を指定します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="e00b7-187">コレクションではなく、が`Customer`返されます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="e00b7-188">クエリでパーティションキーと行キーの両方を指定することは、Table service から単一のエンティティを取得する最速の方法です。</span><span class="sxs-lookup"><span data-stu-id="e00b7-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="e00b7-189">結果は次のように印刷されます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a><span data-ttu-id="e00b7-190">エンティティの置換</span><span class="sxs-lookup"><span data-stu-id="e00b7-190">Replace an entity</span></span>

<span data-ttu-id="e00b7-191">エンティティを更新するには、エンティティを Table service から取得し、エンティティオブジェクトを変更した後、 `Replace`操作を使用して Table service に変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="e00b7-192">これにより、サーバー上でエンティティが完全に置換されます。ただし、取得後にサーバー上のエンティティが変更された場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="e00b7-193">このエラーは、他のソースからの変更がアプリケーションによって誤って上書きされないようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="e00b7-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="e00b7-194">エンティティの挿入または置換</span><span class="sxs-lookup"><span data-stu-id="e00b7-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="e00b7-195">場合によっては、テーブルにエンティティが存在するかどうかがわかりません。</span><span class="sxs-lookup"><span data-stu-id="e00b7-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="e00b7-196">その場合、現在格納されている値は不要になります。</span><span class="sxs-lookup"><span data-stu-id="e00b7-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="e00b7-197">を使用`InsertOrReplace`してエンティティを作成することも、状態に関係なく、エンティティが存在する場合は置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="e00b7-198">エンティティのプロパティのサブセットを照会する</span><span class="sxs-lookup"><span data-stu-id="e00b7-198">Query a subset of entity properties</span></span>

<span data-ttu-id="e00b7-199">テーブルクエリでは、エンティティのすべてではなく、いくつかのプロパティのみを取得できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="e00b7-200">射影と呼ばれるこの手法は、特に大規模なエンティティの場合に、クエリのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="e00b7-201">ここでは、と`DynamicTableEntity` `EntityResolver`を使用して電子メールアドレスのみを返します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="e00b7-202">プロジェクションはローカルストレージエミュレーターではサポートされていないため、このコードは Table service でアカウントを使用している場合にのみ実行します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="e00b7-203">ページ内のエンティティを非同期に取得する</span><span class="sxs-lookup"><span data-stu-id="e00b7-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="e00b7-204">多数のエンティティを読み取っているときに、すべてのエンティティが返されるのを待機するのではなく、取得時に処理する場合は、セグメント化されたクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="e00b7-205">ここでは、非同期ワークフローを使用してページ内の結果を返し、多数の結果が返されるのを待機している間に実行がブロックされないようにします。</span><span class="sxs-lookup"><span data-stu-id="e00b7-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="e00b7-206">ここで、この計算を同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="e00b7-207">エンティティの削除</span><span class="sxs-lookup"><span data-stu-id="e00b7-207">Delete an entity</span></span>

<span data-ttu-id="e00b7-208">エンティティは、取得後に削除できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="e00b7-209">エンティティの更新と同様に、エンティティを取得した後にエンティティが変更された場合、これは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e00b7-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="e00b7-210">テーブルを削除する</span><span class="sxs-lookup"><span data-stu-id="e00b7-210">Delete a table</span></span>

<span data-ttu-id="e00b7-211">ストレージアカウントからテーブルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="e00b7-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="e00b7-212">削除されたテーブルは、削除後の一定期間、再作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="e00b7-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="e00b7-213">次の手順</span><span class="sxs-lookup"><span data-stu-id="e00b7-213">Next steps</span></span>

<span data-ttu-id="e00b7-214">これで、Table storage の基本を学習できました。さらに複雑なストレージタスクと Azure Cosmos DB Table API については、次のリンク先を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e00b7-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="e00b7-215">Azure Cosmos DB Table API の概要</span><span class="sxs-lookup"><span data-stu-id="e00b7-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="e00b7-216">.NET 用ストレージクライアントライブラリのリファレンス</span><span class="sxs-lookup"><span data-stu-id="e00b7-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="e00b7-217">Azure Storage 型プロバイダー</span><span class="sxs-lookup"><span data-stu-id="e00b7-217">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="e00b7-218">Azure Storage チームのブログ</span><span class="sxs-lookup"><span data-stu-id="e00b7-218">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="e00b7-219">接続文字列の構成</span><span class="sxs-lookup"><span data-stu-id="e00b7-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="e00b7-220">.NET での Azure Table Storage のはじめに</span><span class="sxs-lookup"><span data-stu-id="e00b7-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
