---
title: LINQ to SQL のソース コードの分析
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: e34364496a791031cc87cf07efd3d2adca39d93c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743595"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="f69d9-102">LINQ to SQL のソース コードの分析</span><span class="sxs-lookup"><span data-stu-id="f69d9-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="f69d9-103">以下の手順を実行すると、Northwind サンプル データベースから [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のソース コードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f69d9-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="f69d9-104">オブジェクト モデルの要素とデータベースの要素を比較対照することで、個別の項目がどのように対応付けられているかがわかります。</span><span class="sxs-lookup"><span data-stu-id="f69d9-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f69d9-105">Visual Studio を使用している開発者は、このコードを生成するために、O/R デザイナーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f69d9-105">Developers using Visual Studio can use the O/R Designer to produce this code.</span></span>  
  
1. <span data-ttu-id="f69d9-106">開発用コンピューターに Northwind サンプル データベースがない場合は、無料でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f69d9-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="f69d9-107">詳細については、次を参照してください。[サンプル データベースのダウンロード](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="f69d9-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2. <span data-ttu-id="f69d9-108">SqlMetal コマンド ライン ツールを使用して、Visual Basic または C# のソース ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="f69d9-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="f69d9-109">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f69d9-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="f69d9-110">コマンド プロンプトで次のコマンドを入力すると、ストアド プロシージャおよび関数を含めて Visual Basic または C# のソース ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="f69d9-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="f69d9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f69d9-111">See also</span></span>

- [<span data-ttu-id="f69d9-112">参照</span><span class="sxs-lookup"><span data-stu-id="f69d9-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="f69d9-113">背景情報</span><span class="sxs-lookup"><span data-stu-id="f69d9-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
