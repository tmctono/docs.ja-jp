---
title: '方法: DBML ファイルを変更してカスタマイズ コードを生成する'
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: ab49f76a0d5e7338a93e21ae9a8d1d9d74a21e82
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173440"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="6b03e-102">方法: DBML ファイルを変更してカスタマイズ コードを生成する</span><span class="sxs-lookup"><span data-stu-id="6b03e-102">How to: Generate Customized Code by Modifying a DBML File</span></span>

<span data-ttu-id="6b03e-103">データベース マークアップ言語 (.dbml) のメタデータ ファイルから、Visual Basic または C# のソース コードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="6b03e-103">You can generate Visual Basic or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="6b03e-104">この方法を使用すると、アプリケーション マッピング コードを生成する前に、既定の .dbml ファイルをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6b03e-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="6b03e-105">これは高度な機能です。</span><span class="sxs-lookup"><span data-stu-id="6b03e-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="6b03e-106">実行手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b03e-106">The steps in this process are as follows:</span></span>  
  
1. <span data-ttu-id="6b03e-107">.dbml ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="6b03e-107">Generate a .dbml file.</span></span>  
  
2. <span data-ttu-id="6b03e-108">エディターを使用して .dbml ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="6b03e-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="6b03e-109">.dbml ファイルは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の .dbml ファイルのスキーマ定義 (.xsd) ファイルに対して有効である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b03e-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="6b03e-110">詳しくは、「[LINQ to SQL でのコード生成](code-generation-in-linq-to-sql.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b03e-110">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>  
  
3. <span data-ttu-id="6b03e-111">Visual Basic または C# のソース コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="6b03e-111">Generate the Visual Basic or C# source code.</span></span>  
  
 <span data-ttu-id="6b03e-112">次の例では、SQLMetal コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b03e-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="6b03e-113">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b03e-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b03e-114">例</span><span class="sxs-lookup"><span data-stu-id="6b03e-114">Example</span></span>  

 <span data-ttu-id="6b03e-115">次のコードでは、Northwind サンプル データベースから .dbml ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="6b03e-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="6b03e-116">データベース メタデータのソースとして、データベースの名前または .mdf ファイルの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b03e-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```console  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="6b03e-117">例</span><span class="sxs-lookup"><span data-stu-id="6b03e-117">Example</span></span>  

 <span data-ttu-id="6b03e-118">次のコードでは、.dbml ファイルから Visual Basic または C# のソース コードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6b03e-118">The following code generates Visual Basic or C# source code file from a .dbml file.</span></span>  
  
```console
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b03e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b03e-119">See also</span></span>

- [<span data-ttu-id="6b03e-120">LINQ to SQL でのコード生成</span><span class="sxs-lookup"><span data-stu-id="6b03e-120">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="6b03e-121">SqlMetal.exe (コード生成ツール)</span><span class="sxs-lookup"><span data-stu-id="6b03e-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="6b03e-122">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="6b03e-122">Creating the Object Model</span></span>](creating-the-object-model.md)
