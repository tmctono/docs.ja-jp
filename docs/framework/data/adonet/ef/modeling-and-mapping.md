---
title: モデリングとマッピング
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 133539ab1b6d6f2f0ab3f8deed5b22240c2bb07e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854391"
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="ebffe-102">モデリングとマッピング</span><span class="sxs-lookup"><span data-stu-id="ebffe-102">Modeling and Mapping</span></span>
<span data-ttu-id="ebffe-103">Entity Framework では、アプリケーションに最も適した方法で概念モデル、ストレージモデル、およびその2つの間のマッピングを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ebffe-103">In the Entity Framework, you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="ebffe-104">Visual Studio の Entity Data Model ツールを使用すると、を作成できます。データベースまたはグラフィカルモデルからの[edmx ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))。データベースまたはモデルが変更されたときに、そのファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="ebffe-104">The Entity Data Model Tools in Visual Studio allow you to create an .[edmx file](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="ebffe-105">Entity Framework 4.1 以降では、Code First の開発を使用してモデルをプログラムで作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebffe-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="ebffe-106">Code First の開発に対しては、2 つの異なるシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="ebffe-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="ebffe-107">どちらの場合でも、開発者は .NET Framework のクラス定義をコーディングしてモデルを定義し、データ注釈または Fluent API を使用してオプションで追加のマッピングまたは構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebffe-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="ebffe-108">詳細については、「[概念モデルの作成とマッピング](https://go.microsoft.com/fwlink/?LinkId=235016)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebffe-108">For more information, see [Creating and Mapping a Conceptual Model](https://go.microsoft.com/fwlink/?LinkId=235016).</span></span>  
  
 <span data-ttu-id="ebffe-109">.NET Framework に含まれている EDM ジェネレーターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebffe-109">You can also use the EDM Generator, which is included with the .NET Framework.</span></span> <span data-ttu-id="ebffe-110">EdmGen.exe は、既存のデータ ソースから .csdl ファイル、.ssdl ファイル、および .msl ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="ebffe-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="ebffe-111">モデルとマッピングの内容を手動で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebffe-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="ebffe-112">詳細については、「 [EDM Generator (edmgen.exe)](edm-generator-edmgen-exe.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebffe-112">For more information, see [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md).</span></span>
