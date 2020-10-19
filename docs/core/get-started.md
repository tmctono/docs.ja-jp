---
title: .NET の使用を開始する
description: Hello World .NET アプリを作成します。
author: adegeo
ms.author: adegeo
ms.date: 09/29/2020
ms.custom: vs-dotnet
ms.openlocfilehash: 6ad2b96e668c52ee80b707e31a63eac2433f3c9e
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756092"
---
# <a name="get-started-with-net"></a><span data-ttu-id="3ba35-103">.NET を使って作業を開始する</span><span class="sxs-lookup"><span data-stu-id="3ba35-103">Get started with .NET</span></span>

<span data-ttu-id="3ba35-104">この記事では、"Hello World!" .NET アプリを作成して実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ba35-104">This article teaches you how to create and run a "Hello World!"</span></span> .NET app.

<span data-ttu-id="3ba35-106">.NET についてよくわからない場合は、[.NET の概要](introduction.md)のページからお読みください。</span><span class="sxs-lookup"><span data-stu-id="3ba35-106">If you're unsure what .NET is, start with the [.NET introduction](introduction.md).</span></span>

## <a name="create-an-application"></a><span data-ttu-id="3ba35-107">アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="3ba35-107">Create an application</span></span>

<span data-ttu-id="3ba35-108">まず、ご利用のコンピューターで [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="3ba35-108">First, download and install the [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core) on your computer.</span></span>

<span data-ttu-id="3ba35-109">次に、**PowerShell**、**コマンド プロンプト**、**bash** などのターミナルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ba35-109">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="3ba35-110">次の `dotnet` コマンドを入力し、C# アプリケーションを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="3ba35-110">Enter the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="3ba35-111">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ba35-111">You see the following output:</span></span>

```output
Hello World!
```

<span data-ttu-id="3ba35-112">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="3ba35-112">Congratulations!</span></span> <span data-ttu-id="3ba35-113">シンプルな .NET アプリケーションを作成しました。</span><span class="sxs-lookup"><span data-stu-id="3ba35-113">You've created a simple .NET application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ba35-114">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3ba35-114">Next steps</span></span>

<span data-ttu-id="3ba35-115">[ステップバイステップのチュートリアル](../standard/get-started.md)に従って、または YouTube で [.NET 101 の動画](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80)を視聴して、.NET アプリケーションの開発を開始します。</span><span class="sxs-lookup"><span data-stu-id="3ba35-115">Get started developing .NET applications by following a [step-by-step tutorial](../standard/get-started.md) or by watching [.NET 101 videos](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) on YouTube.</span></span>
