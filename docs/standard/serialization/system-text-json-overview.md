---
title: .NET での JSON のシリアル化
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 6cb45fded220b6123dbf4461f5f1cf1c3556ff69
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083094"
---
# <a name="json-serialization-in-net"></a><span data-ttu-id="be3e1-102">.NET での JSON のシリアル化</span><span class="sxs-lookup"><span data-stu-id="be3e1-102">JSON serialization in .NET</span></span>

<span data-ttu-id="be3e1-103">名前`System.Text.Json`空間は、JavaScript Object Notation (JSON) との間でシリアル化およびシリアル化を行うための機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="be3e1-103">The `System.Text.Json` namespace provides functionality for serializing to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="be3e1-104">ライブラリの設計では、高度な機能セットに対する高パフォーマンスと低メモリ割り当てが強調されています。</span><span class="sxs-lookup"><span data-stu-id="be3e1-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="be3e1-105">組み込みの UTF-8 サポートは、UTF-8 としてエンコードされた JSON テキストの読み取りと書き込みのプロセスを最適化します。これは、web 上のデータおよびディスク上のファイルのための最も一般的なエンコードです。</span><span class="sxs-lookup"><span data-stu-id="be3e1-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="be3e1-106">ライブラリには、メモリ内のドキュメントオブジェクトモデル (DOM) を操作するためのクラスも用意されています。</span><span class="sxs-lookup"><span data-stu-id="be3e1-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="be3e1-107">この機能により、JSON ファイルまたは文字列内の要素に対する読み取り専用のランダムアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="be3e1-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="be3e1-108">ライブラリを取得する方法</span><span class="sxs-lookup"><span data-stu-id="be3e1-108">How to get the library</span></span>

* <span data-ttu-id="be3e1-109">このライブラリは、 [.Net Core 3.0](https://aka.ms/netcore3download)共有フレームワークの一部として組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="be3e1-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="be3e1-110">その他のターゲットフレームワークの場合[は、System.string NuGet パッケージ](https://www.nuget.org/packages/System.Text.Json)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="be3e1-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="be3e1-111">パッケージは次をサポートします。</span><span class="sxs-lookup"><span data-stu-id="be3e1-111">The package supports:</span></span>
  * <span data-ttu-id="be3e1-112">.NET Standard 2.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="be3e1-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="be3e1-113">.NET Framework 4.61 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="be3e1-113">.NET Framework 4.61 and later versions</span></span>
  * <span data-ttu-id="be3e1-114">.NET Core 2.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="be3e1-114">.NET Core 2.0 and later versions</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be3e1-115">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="be3e1-115">Additional resources</span></span>

* [<span data-ttu-id="be3e1-116">ライブラリの使用方法</span><span class="sxs-lookup"><span data-stu-id="be3e1-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="be3e1-117">ソース コード</span><span class="sxs-lookup"><span data-stu-id="be3e1-117">Source code</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [<span data-ttu-id="be3e1-118">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="be3e1-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="be3e1-119">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="be3e1-119">Roadmap</span></span>](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="be3e1-120">Dotnet/corefx リポジトリでの GitHub の問題</span><span class="sxs-lookup"><span data-stu-id="be3e1-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="be3e1-121">System.string の開発についての説明</span><span class="sxs-lookup"><span data-stu-id="be3e1-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115)
  * [<span data-ttu-id="be3e1-122">すべての system.string の問題</span><span class="sxs-lookup"><span data-stu-id="be3e1-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="be3e1-123">Json のラベル付きの問題-doc</span><span class="sxs-lookup"><span data-stu-id="be3e1-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc)
