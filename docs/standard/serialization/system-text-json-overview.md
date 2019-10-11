---
title: .Net を使用してC# JSON をシリアル化および逆シリアル化する
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 5ce98a7908470a402779436db43333d46f5101fc
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180152"
---
# <a name="json-serialization-in-net---overview"></a><span data-ttu-id="7fccc-102">.NET での JSON のシリアル化-概要</span><span class="sxs-lookup"><span data-stu-id="7fccc-102">JSON serialization in .NET - overview</span></span>

<span data-ttu-id="7fccc-103">@No__t-0 名前空間は、JavaScript Object Notation (JSON) との間でシリアル化および逆シリアル化を行うための機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7fccc-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="7fccc-104">ライブラリの設計では、高度な機能セットに対する高パフォーマンスと低メモリ割り当てが強調されています。</span><span class="sxs-lookup"><span data-stu-id="7fccc-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="7fccc-105">組み込みの UTF-8 サポートは、UTF-8 としてエンコードされた JSON テキストの読み取りと書き込みのプロセスを最適化します。これは、web 上のデータおよびディスク上のファイルのための最も一般的なエンコードです。</span><span class="sxs-lookup"><span data-stu-id="7fccc-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="7fccc-106">ライブラリには、メモリ内のドキュメントオブジェクトモデル (DOM) を操作するためのクラスも用意されています。</span><span class="sxs-lookup"><span data-stu-id="7fccc-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="7fccc-107">この機能により、JSON ファイルまたは文字列内の要素に対する読み取り専用のランダムアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="7fccc-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="7fccc-108">ライブラリを取得する方法</span><span class="sxs-lookup"><span data-stu-id="7fccc-108">How to get the library</span></span>

* <span data-ttu-id="7fccc-109">このライブラリは、 [.Net Core 3.0](https://aka.ms/netcore3download)共有フレームワークの一部として組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="7fccc-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="7fccc-110">その他のターゲットフレームワークの場合[は、System.string NuGet パッケージ](https://www.nuget.org/packages/System.Text.Json)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7fccc-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="7fccc-111">パッケージは次をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7fccc-111">The package supports:</span></span>
  * <span data-ttu-id="7fccc-112">.NET Standard 2.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="7fccc-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="7fccc-113">4\.6.1 以降のバージョンの .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7fccc-113">.NET Framework 4.6.1 and later versions</span></span>
  * <span data-ttu-id="7fccc-114">.NET Core 2.0、2.1、および2.2</span><span class="sxs-lookup"><span data-stu-id="7fccc-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7fccc-115">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="7fccc-115">Additional resources</span></span>

* [<span data-ttu-id="7fccc-116">ライブラリの使用方法</span><span class="sxs-lookup"><span data-stu-id="7fccc-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="7fccc-117">ソース コード</span><span class="sxs-lookup"><span data-stu-id="7fccc-117">Source code</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [<span data-ttu-id="7fccc-118">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="7fccc-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="7fccc-119">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="7fccc-119">Roadmap</span></span>](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="7fccc-120">Dotnet/corefx リポジトリでの GitHub の問題</span><span class="sxs-lookup"><span data-stu-id="7fccc-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="7fccc-121">System.string の開発についての説明</span><span class="sxs-lookup"><span data-stu-id="7fccc-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115)
  * [<span data-ttu-id="7fccc-122">すべての system.string の問題</span><span class="sxs-lookup"><span data-stu-id="7fccc-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="7fccc-123">Json のラベル付きの問題-doc</span><span class="sxs-lookup"><span data-stu-id="7fccc-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc)
