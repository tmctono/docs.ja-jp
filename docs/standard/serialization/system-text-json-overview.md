---
title: .Net を使用してC# JSON をシリアル化および逆シリアル化する
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 6561d5e1580e1170369622ebc7bb330ff4e0964f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705783"
---
# <a name="json-serialization-in-net---overview"></a><span data-ttu-id="62256-102">.NET での JSON のシリアル化-概要</span><span class="sxs-lookup"><span data-stu-id="62256-102">JSON serialization in .NET - overview</span></span>

<span data-ttu-id="62256-103">`System.Text.Json` 名前空間は、JavaScript Object Notation (JSON) にシリアル化および逆シリアル化する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="62256-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="62256-104">ライブラリの設計では、高度な機能セットに対する高パフォーマンスと低メモリ割り当てが強調されています。</span><span class="sxs-lookup"><span data-stu-id="62256-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="62256-105">組み込みの UTF-8 サポートは、UTF-8 としてエンコードされた JSON テキストの読み取りと書き込みのプロセスを最適化します。これは、web 上のデータおよびディスク上のファイルのための最も一般的なエンコードです。</span><span class="sxs-lookup"><span data-stu-id="62256-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="62256-106">ライブラリには、メモリ内のドキュメントオブジェクトモデル (DOM) を操作するためのクラスも用意されています。</span><span class="sxs-lookup"><span data-stu-id="62256-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="62256-107">この機能により、JSON ファイルまたは文字列内の要素に対する読み取り専用のランダムアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="62256-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="62256-108">ライブラリを取得する方法</span><span class="sxs-lookup"><span data-stu-id="62256-108">How to get the library</span></span>

* <span data-ttu-id="62256-109">このライブラリは、 [.Net Core 3.0](https://aka.ms/netcore3download)共有フレームワークの一部として組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="62256-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="62256-110">その他のターゲットフレームワークの場合[は、System.string NuGet パッケージ](https://www.nuget.org/packages/System.Text.Json)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="62256-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="62256-111">パッケージは次をサポートします。</span><span class="sxs-lookup"><span data-stu-id="62256-111">The package supports:</span></span>
  * <span data-ttu-id="62256-112">.NET Standard 2.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="62256-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="62256-113">4\.6.1 以降のバージョンの .NET Framework</span><span class="sxs-lookup"><span data-stu-id="62256-113">.NET Framework 4.6.1 and later versions</span></span>
  * <span data-ttu-id="62256-114">.NET Core 2.0、2.1、および2.2</span><span class="sxs-lookup"><span data-stu-id="62256-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62256-115">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="62256-115">Additional resources</span></span>

* [<span data-ttu-id="62256-116">ライブラリの使用方法</span><span class="sxs-lookup"><span data-stu-id="62256-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="62256-117">ソース コード</span><span class="sxs-lookup"><span data-stu-id="62256-117">Source code</span></span>](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Text.Json)
* [<span data-ttu-id="62256-118">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="62256-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="62256-119">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="62256-119">Roadmap</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="62256-120">Dotnet/corefx リポジトリでの GitHub の問題</span><span class="sxs-lookup"><span data-stu-id="62256-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="62256-121">System.string の開発についての説明</span><span class="sxs-lookup"><span data-stu-id="62256-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115) <!-- TODO: Issues are still not moved to the new repo-->
  * [<span data-ttu-id="62256-122">すべての system.string の問題</span><span class="sxs-lookup"><span data-stu-id="62256-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="62256-123">Json のラベル付きの問題-doc</span><span class="sxs-lookup"><span data-stu-id="62256-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/runtime/labels/json-functionality-doc)
