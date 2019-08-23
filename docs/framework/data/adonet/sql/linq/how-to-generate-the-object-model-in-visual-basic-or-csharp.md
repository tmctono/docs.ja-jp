---
title: '方法: Visual Basic または C# でオブジェクト モデルを生成する'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 5f2c2f99a5efeb3463ecf5bf401a6cf654845bb2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911968"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="199fe-102">方法: Visual Basic または C でオブジェクトモデルを生成する\#</span><span class="sxs-lookup"><span data-stu-id="199fe-102">How to: Generate the Object Model in Visual Basic or C\#</span></span>
<span data-ttu-id="199fe-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、使用しているプログラミング言語のオブジェクト モデルが、リレーショナル データベースに対応付けられています。</span><span class="sxs-lookup"><span data-stu-id="199fe-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="199fe-104">既存のデータベースのメタデータから Visual Basic またはC#モデルを自動的に生成するために、2つのツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="199fe-104">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
- <span data-ttu-id="199fe-105">Visual Studio を使用している場合は、オブジェクトリレーショナルデザイナーを使用してオブジェクトモデルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="199fe-105">If you are using Visual Studio, you can use the Object Relational Designer to generate an object model.</span></span> <span data-ttu-id="199fe-106">O/R デザイナーには、オブジェクトモデルを[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]生成するのに役立つ豊富なユーザーインターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="199fe-106">The O/R Designer provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="199fe-107">詳細については、「 [Visual Studio の Linq TO SQL ツール](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="199fe-107">For more information see, [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
- <span data-ttu-id="199fe-108">SQLMetal コマンド ライン ツール。</span><span class="sxs-lookup"><span data-stu-id="199fe-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="199fe-109">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="199fe-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="199fe-110">既存のデータベースがなく、オブジェクト モデルからデータベースを作成する場合は、コード エディターと <xref:System.Data.Linq.DataContext.CreateDatabase%2A> を使用してオブジェクト モデルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="199fe-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="199fe-111">詳細については、「[方法 :データベース](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)を動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="199fe-111">For more information, see [How to: Dynamically Create a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="199fe-112">O/R デザイナーのドキュメントでは、O/R デザイナーを使用しC#て Visual Basic またはオブジェクトモデルを生成する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="199fe-112">Documentation for the O/R Designer provides examples of how to generate a Visual Basic or C# object model by using the O/R Designer.</span></span> <span data-ttu-id="199fe-113">以下の情報は、SQLMetal コマンド ライン ツールの使用方法の例です。</span><span class="sxs-lookup"><span data-stu-id="199fe-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="199fe-114">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="199fe-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="199fe-115">例</span><span class="sxs-lookup"><span data-stu-id="199fe-115">Example</span></span>  
 <span data-ttu-id="199fe-116">次の例に示す SQLMetal コマンドラインでは、Northwind サンプルデータベースの属性ベースのオブジェクトモデルとして Visual Basic コードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="199fe-116">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="199fe-117">ストアド プロシージャと関数も含まれます。</span><span class="sxs-lookup"><span data-stu-id="199fe-117">Stored procedures and functions are also rendered.</span></span>  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="199fe-118">例</span><span class="sxs-lookup"><span data-stu-id="199fe-118">Example</span></span>  
 <span data-ttu-id="199fe-119">次の例に示す SQLMetal コマンド ラインでは、Northwind サンプル データベースの属性ベースのオブジェクト モデルとして C# コードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="199fe-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="199fe-120">ストアド プロシージャと関数も含まれ、テーブル名は自動的に複数化されます。</span><span class="sxs-lookup"><span data-stu-id="199fe-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="199fe-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="199fe-121">See also</span></span>

- [<span data-ttu-id="199fe-122">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="199fe-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)
- [<span data-ttu-id="199fe-123">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="199fe-123">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="199fe-124">チュートリアルによる学習</span><span class="sxs-lookup"><span data-stu-id="199fe-124">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [<span data-ttu-id="199fe-125">方法: コードエディターを使用してエンティティクラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="199fe-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
- [<span data-ttu-id="199fe-126">属性ベースの対応付け</span><span class="sxs-lookup"><span data-stu-id="199fe-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [<span data-ttu-id="199fe-127">SqlMetal.exe (コード生成ツール)</span><span class="sxs-lookup"><span data-stu-id="199fe-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="199fe-128">外部マップ</span><span class="sxs-lookup"><span data-stu-id="199fe-128">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
- [<span data-ttu-id="199fe-129">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="199fe-129">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="199fe-130">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="199fe-130">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
