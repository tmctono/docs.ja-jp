---
title: '方法: 複合型を返すクエリを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: a428f54c3834ccdf6a0c7a5bfce8307172724524
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322889"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="f1f38-102">方法: 複合型を返すクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="f1f38-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="f1f38-103">このトピックでは、複合型プロパティを含むエンティティ型オブジェクトを返す [!INCLUDE[esql](../../../../../includes/esql-md.md)] クエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f38-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="f1f38-104">この例のコードを実行するには</span><span class="sxs-lookup"><span data-stu-id="f1f38-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="f1f38-105">追加、 [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)をプロジェクトに使用するプロジェクトを構成して、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f1f38-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="f1f38-106">詳細については、「[方法 :エンティティ データ モデル ウィザードを使用して](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="f1f38-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="f1f38-107">アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="f1f38-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="f1f38-108">モデルを表示する .edmx ファイルをダブルクリック、[モデル ブラウザー ウィンドウ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100))エンティティ デザイナーの。</span><span class="sxs-lookup"><span data-stu-id="f1f38-108">Double click the .edmx file to display the model in the [Model Browser window](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) of the Entity Designer.</span></span> <span data-ttu-id="f1f38-109">エンティティ デザイナー画面で選択、`Email`と`Phone`のプロパティ、`Contact`エンティティ型、し、右クリックして選択**新しい複合型へのリファクター**します。</span><span class="sxs-lookup"><span data-stu-id="f1f38-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4. <span data-ttu-id="f1f38-110">選択した場合は、新しい複合型`Email`と`Phone`にプロパティを追加、**モデル ブラウザー**します。</span><span class="sxs-lookup"><span data-stu-id="f1f38-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="f1f38-111">複合型が既定の名前を指定: 型の名前を変更`EmailPhone`で、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="f1f38-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="f1f38-112">また、新しい `ComplexProperty` プロパティが `Contact` エンティティ型に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f1f38-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="f1f38-113">プロパティの名前を `EmailPhoneComplexType.` に変更します。</span><span class="sxs-lookup"><span data-stu-id="f1f38-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="f1f38-114">作成して、Entity Data Model ウィザードを使用した複合型の変更については、次を参照してください。[方法。既存のプロパティを複合型プロパティにリファクタリング](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100))と[方法。作成し、複合型を変更](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="f1f38-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) and [How to: Create and Modify Complex Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1f38-115">例</span><span class="sxs-lookup"><span data-stu-id="f1f38-115">Example</span></span>  
 <span data-ttu-id="f1f38-116">次の例のコレクションを返すクエリを実行する`Contact`オブジェクトし、の 2 つのプロパティを表示、`Contact`オブジェクト:`ContactID`との値、`EmailPhoneComplexType`複合型。</span><span class="sxs-lookup"><span data-stu-id="f1f38-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
