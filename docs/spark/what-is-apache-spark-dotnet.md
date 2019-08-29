---
title: .NET for Apache Spark とは
description: .NET for Apache Spark について説明します。これは、.NET コードが記述されたすべての場所で Spark を使用する、無料でオープンソースのクロスプラットフォームなビッグ データ分析フレームワークです。
author: mamccrea
ms.topic: overview
ms.date: 05/06/2019
ms.openlocfilehash: e72a1fe196b4374903146fd439033d5dafb83eaf
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "69576889"
---
# <a name="what-is-net-for-apache-spark"></a><span data-ttu-id="26292-103">.NET for Apache Spark とは</span><span class="sxs-lookup"><span data-stu-id="26292-103">What is .NET for Apache Spark?</span></span>

<span data-ttu-id="26292-104">[Apache Spark](https://spark.apache.org/) は、大規模なデータ セット (一般的にテラバイトまたはペタバイト規模のデータ) の分析に使用される汎用の分散処理エンジンです。</span><span class="sxs-lookup"><span data-stu-id="26292-104">[Apache Spark](https://spark.apache.org/) is a general-purpose distributed processing engine for analytics over large data sets-typically terabytes or petabytes of data.</span></span> <span data-ttu-id="26292-105">.NET for Apache Spark により、開発者が Apache Spark を利用できるようになり、既知の言語をサポートしているお使いのアプリケーションに Spark の機能を組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="26292-105">.NET for Apache Spark makes Apache Spark accessible for developers, bringing the power of Spark to your applications with support for languages you already know.</span></span>

<span data-ttu-id="26292-106">C# および F# では、次にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="26292-106">With C# and F#, you can access:</span></span>

* <span data-ttu-id="26292-107">構造化データを操作するためのデータフレームおよび SparkSQL。</span><span class="sxs-lookup"><span data-stu-id="26292-107">Dataframe and SparkSQL for working with structured data.</span></span>
* <span data-ttu-id="26292-108">ストリーミング データを操作するための Spark Structured Streaming。</span><span class="sxs-lookup"><span data-stu-id="26292-108">Spark Structured Streaming for working with streaming data.</span></span>

<span data-ttu-id="26292-109">.NET for Apache Spark は、.NET Standard (.NET 実装全体で共通した .NET API の標準仕様) に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="26292-109">.NET for Apache Spark is compliant with .NET Standard, a formal specification of .NET APIs that are common across .NET implementations.</span></span> <span data-ttu-id="26292-110">つまり、.NET コードが記述されたすべての場所で Apache Spark を使用できることで、.NET 開発者として既に持っているすべての知識、スキル、コード、およびライブラリを再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="26292-110">This means you can use .NET for Apache Spark anywhere you write .NET code allowing you to reuse all the knowledge, skills, code, and libraries you already have as a .NET developer.</span></span>

<span data-ttu-id="26292-111">.NET for Apache Spark は、.NET Core を使用して Windows、Linux、macOS で実行されます。</span><span class="sxs-lookup"><span data-stu-id="26292-111">.NET for Apache Spark runs on Windows, Linux, and macOS using .NET Core.</span></span> <span data-ttu-id="26292-112">Windows では、.NET Framework を使用して実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="26292-112">It also runs on Windows using .NET Framework.</span></span> <span data-ttu-id="26292-113">Azure HDInsight Spark、Amazon EMR Spark、Azure Databricks、AWS 上の Databricks など、主要なすべてのクラウド プロバイダーにアプリケーションをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="26292-113">You can deploy your applications to all major cloud providers including Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks, and Databricks on AWS.</span></span>

## <a name="net-foundation"></a><span data-ttu-id="26292-114">.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="26292-114">.NET Foundation</span></span>

<span data-ttu-id="26292-115">.NET for Apache Spark プロジェクトは、[.NET Foundation](https://www.dotnetfoundation.org/) の一部です。</span><span class="sxs-lookup"><span data-stu-id="26292-115">The .NET for Apache Spark project is part of the [.NET Foundation](https://www.dotnetfoundation.org/).</span></span>

## <a name="contributions"></a><span data-ttu-id="26292-116">投稿</span><span class="sxs-lookup"><span data-stu-id="26292-116">Contributions</span></span>

<span data-ttu-id="26292-117">.NET for Apache Spark チームでは、GitHub イシューとプル要求の両方での投稿を推奨しています。</span><span class="sxs-lookup"><span data-stu-id="26292-117">The .NET for Apache Spark team encourages contributions, both GitHub issues and pull requests.</span></span> <span data-ttu-id="26292-118">まず、[既存のイシュー](https://github.com/dotnet/spark/issues)を探します。</span><span class="sxs-lookup"><span data-stu-id="26292-118">First, look for an [existing issue](https://github.com/dotnet/spark/issues).</span></span> <span data-ttu-id="26292-119">既存のイシューが見つからない場合は、[新しいイシューを開始](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+)します。</span><span class="sxs-lookup"><span data-stu-id="26292-119">If you can't find an existing issue, [open a new issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span></span>
