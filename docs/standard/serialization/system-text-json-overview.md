---
title: C# を使用した JSON のシリアル化と逆シリアル化 - .NET
description: この概要では、.NET で JSON との間でシリアル化または逆シリアル化を行うための System.Text.Json 名前空間機能について説明します。
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 909d979d46b30939e304af071de65d230febd92d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380137"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="fc15a-103">.NET での JSON のシリアル化と逆シリアル化 (マーシャリングとマーシャリング解除) - 概要</span><span class="sxs-lookup"><span data-stu-id="fc15a-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="fc15a-104">`System.Text.Json` 名前空間は、JavaScript Object Notation (JSON) との間でのシリアル化と逆シリアル化の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc15a-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="fc15a-105">ライブラリの設計では、ハイ パフォーマンスと、高度な豊富なセットに対する少ないメモリ割り当てが強調されています。</span><span class="sxs-lookup"><span data-stu-id="fc15a-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="fc15a-106">組み込みの UTF-8 サポートによって、UTF-8 としてエンコードされた JSON テキストの読み取りと書き込みのプロセスが最適化されます。これは、web 上のデータおよびディスク上のファイルのための最も一般的なエンコードです。</span><span class="sxs-lookup"><span data-stu-id="fc15a-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="fc15a-107">ライブラリには、メモリ内のドキュメント オブジェクト モデル (DOM) を操作するためのクラスも用意されています。</span><span class="sxs-lookup"><span data-stu-id="fc15a-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="fc15a-108">この機能により、JSON ファイルまたは文字列内の要素に対する読み取り専用のランダムアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="fc15a-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="fc15a-109">ライブラリの入手方法</span><span class="sxs-lookup"><span data-stu-id="fc15a-109">How to get the library</span></span>

* <span data-ttu-id="fc15a-110">このライブラリは [.NET Core 3.0](https://aka.ms/netcore3download) 共有フレームワークの一部として組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="fc15a-110">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="fc15a-111">その他のターゲット フレームワークの場合は、[System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fc15a-111">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="fc15a-112">このパッケージで以下がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="fc15a-112">The package supports:</span></span>
  * <span data-ttu-id="fc15a-113">.NET Standard 2.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="fc15a-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="fc15a-114">.NET Framework 4.7.2 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="fc15a-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="fc15a-115">.NET Core 2.0、2.1、および 2.2</span><span class="sxs-lookup"><span data-stu-id="fc15a-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fc15a-116">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="fc15a-116">Additional resources</span></span>

* [<span data-ttu-id="fc15a-117">ライブラリを使用する方法</span><span class="sxs-lookup"><span data-stu-id="fc15a-117">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="fc15a-118">[Newtonsoft.Json から移行する方法](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="fc15a-118">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="fc15a-119">コンバーターを記述する方法</span><span class="sxs-lookup"><span data-stu-id="fc15a-119">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="fc15a-120">[System.Text.Json ソース コード](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="fc15a-120">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="fc15a-121">[System.Text.Json API リファレンス](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="fc15a-121">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="fc15a-122">[System.Text.Json.Serialization API リファレンス](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="fc15a-122">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
