---
title: .Net を使用してC# JSON をシリアル化および逆シリアル化する
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c05783963ba521109fb542f247ec9e62fdb5c2d9
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904640"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="52617-102">.NET での JSON のシリアル化と逆シリアル化 (マーシャリングとアンマーシャリング)-概要</span><span class="sxs-lookup"><span data-stu-id="52617-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="52617-103">`System.Text.Json` 名前空間は、JavaScript Object Notation (JSON) にシリアル化および逆シリアル化する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="52617-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="52617-104">ライブラリの設計では、高度な機能セットに対する高パフォーマンスと低メモリ割り当てが強調されています。</span><span class="sxs-lookup"><span data-stu-id="52617-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="52617-105">組み込みの UTF-8 サポートは、UTF-8 としてエンコードされた JSON テキストの読み取りと書き込みのプロセスを最適化します。これは、web 上のデータおよびディスク上のファイルのための最も一般的なエンコードです。</span><span class="sxs-lookup"><span data-stu-id="52617-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="52617-106">ライブラリには、メモリ内のドキュメントオブジェクトモデル (DOM) を操作するためのクラスも用意されています。</span><span class="sxs-lookup"><span data-stu-id="52617-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="52617-107">この機能により、JSON ファイルまたは文字列内の要素に対する読み取り専用のランダムアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="52617-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="52617-108">ライブラリを取得する方法</span><span class="sxs-lookup"><span data-stu-id="52617-108">How to get the library</span></span>

* <span data-ttu-id="52617-109">このライブラリは、 [.Net Core 3.0](https://aka.ms/netcore3download)共有フレームワークの一部として組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="52617-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="52617-110">その他のターゲットフレームワークの場合[は、System.string NuGet パッケージ](https://www.nuget.org/packages/System.Text.Json)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="52617-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="52617-111">パッケージは次をサポートします。</span><span class="sxs-lookup"><span data-stu-id="52617-111">The package supports:</span></span>
  * <span data-ttu-id="52617-112">.NET Standard 2.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="52617-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="52617-113">4\.7.2 以降のバージョンの .NET Framework</span><span class="sxs-lookup"><span data-stu-id="52617-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="52617-114">.NET Core 2.0、2.1、および2.2</span><span class="sxs-lookup"><span data-stu-id="52617-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52617-115">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="52617-115">Additional resources</span></span>

* [<span data-ttu-id="52617-116">ライブラリの使用方法</span><span class="sxs-lookup"><span data-stu-id="52617-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="52617-117">Newtonsoft. Json から移行する方法</span><span class="sxs-lookup"><span data-stu-id="52617-117">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="52617-118">方法 (コンバーターを記述する)</span><span class="sxs-lookup"><span data-stu-id="52617-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="52617-119">System.string のソースコード</span><span class="sxs-lookup"><span data-stu-id="52617-119">System.Text.Json source code</span></span>](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [<span data-ttu-id="52617-120">System.string API リファレンス</span><span class="sxs-lookup"><span data-stu-id="52617-120">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="52617-121">Text. Json. Serialization API リファレンス</span><span class="sxs-lookup"><span data-stu-id="52617-121">System.Text.Json.Serialization API reference</span></span>](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
