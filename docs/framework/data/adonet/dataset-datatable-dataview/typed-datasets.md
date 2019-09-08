---
title: 型指定されたデータセット
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 7c8111e0e62a57b6745a5ea0387fc65a05839df8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785841"
---
# <a name="typed-datasets"></a><span data-ttu-id="075b1-102">型指定されたデータセット</span><span class="sxs-lookup"><span data-stu-id="075b1-102">Typed DataSets</span></span>
<span data-ttu-id="075b1-103">厳密に型指定されていない変数を使用した値への遅延バインディング アクセスに加えて、<xref:System.Data.DataSet> には、厳密に型指定された変数を使用したデータへのアクセスも用意されています。</span><span class="sxs-lookup"><span data-stu-id="075b1-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="075b1-104">**データセット**の一部であるテーブルと列には、ユーザーフレンドリな名前と厳密に型指定された変数を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="075b1-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="075b1-105">型指定された**データセット**は、**データセット**から派生するクラスです。</span><span class="sxs-lookup"><span data-stu-id="075b1-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="075b1-106">そのため、**データセット**のすべてのメソッド、イベント、およびプロパティを継承します。</span><span class="sxs-lookup"><span data-stu-id="075b1-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="075b1-107">さらに、型指定された**データセット**は、厳密に型指定されたメソッド、イベント、およびプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="075b1-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="075b1-108">つまり、コレクションベースのメソッドを使用せずに名前でテーブルおよび列にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="075b1-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="075b1-109">コードを読みやすくするだけではありませんが、型指定された**データセット**を使用すると、入力に応じて自動的に行を補完することができます。</span><span class="sxs-lookup"><span data-stu-id="075b1-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="075b1-110">また、厳密に型指定された**データセット**は、コンパイル時に適切な型として値にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="075b1-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="075b1-111">厳密に型指定された**データセット**では、実行時ではなく、コードがコンパイルされると、型の不一致エラーがキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="075b1-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="075b1-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="075b1-112">In This Section</span></span>  
 [<span data-ttu-id="075b1-113">厳密に型指定された DataSet の生成</span><span class="sxs-lookup"><span data-stu-id="075b1-113">Generating Strongly Typed DataSets</span></span>](generating-strongly-typed-datasets.md)  
 <span data-ttu-id="075b1-114">厳密に型指定された**データセット**を作成して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="075b1-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="075b1-115">型指定された DataSet の注釈</span><span class="sxs-lookup"><span data-stu-id="075b1-115">Annotating Typed DataSets</span></span>](annotating-typed-datasets.md)  
 <span data-ttu-id="075b1-116">厳密に型指定された**データセット**を生成するために使用する XML スキーマ定義言語 (XSD) スキーマに注釈を付けて、基になるスキーマを変更せずに**データセット**要素にわかりやすい名前を付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="075b1-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="075b1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="075b1-117">See also</span></span>

- [<span data-ttu-id="075b1-118">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="075b1-118">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="075b1-119">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="075b1-119">ADO.NET Overview</span></span>](../ado-net-overview.md)
