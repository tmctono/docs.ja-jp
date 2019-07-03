---
title: '方法: クエリを使用してモデル定義関数を呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: 32cdb5b0f27817856ab586eb38f89df63c1c4d3b
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539861"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="3a7ad-102">方法: クエリを使用してモデル定義関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="3a7ad-102">How to: Call Model-Defined Functions in Queries</span></span>
<span data-ttu-id="3a7ad-103">このトピックでは、概念モデルから linq to Entities クエリで定義されている関数を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-103">This topic describes how to call functions that are defined in the conceptual model from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="3a7ad-104">次の手順では、モデル定義関数から、linq to Entities クエリを呼び出すことの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-104">The procedure below provides a high-level outline for calling a model-defined function from within a LINQ to Entities query.</span></span> <span data-ttu-id="3a7ad-105">各手順の詳しい説明は、その後の例で示します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="3a7ad-106">この手順では、関数を概念モデルで定義済みであると想定します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="3a7ad-107">詳細については、「[方法 :概念モデルでカスタム関数を定義](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="3a7ad-108">概念モデルで定義された関数を呼び出すには</span><span class="sxs-lookup"><span data-stu-id="3a7ad-108">To call a function defined in the conceptual model</span></span>  
  
1. <span data-ttu-id="3a7ad-109">概念モデルで定義された関数にマップされているアプリケーションに、共通言語ランタイム (CLR) メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="3a7ad-110">メソッドをマップするには、ユーザーが <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> をメソッドに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="3a7ad-111">属性の <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> パラメーターと <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> パラメーターが、それぞれ概念モデルの名前空間名と関数名であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="3a7ad-112">LINQ の関数名解決では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2. <span data-ttu-id="3a7ad-113">LINQ to Entities クエリから関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-113">Call the function in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a7ad-114">例</span><span class="sxs-lookup"><span data-stu-id="3a7ad-114">Example</span></span>  
 <span data-ttu-id="3a7ad-115">次の例では、概念モデルから、linq to Entities クエリで定義されている関数を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a LINQ to Entities query.</span></span> <span data-ttu-id="3a7ad-116">この例では、School モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-116">The example uses the School model.</span></span> <span data-ttu-id="3a7ad-117">School モデルについては、次を参照してください。 [School サンプル データベースの作成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))と[School .edmx ファイルを生成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-117">For information about the School model, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>  
  
 <span data-ttu-id="3a7ad-118">次の概念モデル関数は、あるインストラクターが雇用されてから経過した年数を返します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="3a7ad-119">概念モデルに関数を追加する方法の詳細については、次を参照してください。[方法。概念モデルでカスタム関数を定義](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)))。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="3a7ad-120">例</span><span class="sxs-lookup"><span data-stu-id="3a7ad-120">Example</span></span>  
 <span data-ttu-id="3a7ad-121">次に、次のメソッドをアプリケーションに追加し、<xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> を使用して概念モデル関数にマップします。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="3a7ad-122">例</span><span class="sxs-lookup"><span data-stu-id="3a7ad-122">Example</span></span>  
 <span data-ttu-id="3a7ad-123">今すぐから概念モデルの関数を linq to Entities クエリを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-123">Now you can call the conceptual model function from within a LINQ to Entities query.</span></span> <span data-ttu-id="3a7ad-124">次のコードは、雇用年数が 10 年を超えるすべてのインストラクターを表示するメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3a7ad-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3a7ad-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a7ad-125">See also</span></span>

- <span data-ttu-id="3a7ad-126">[.edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3a7ad-126">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="3a7ad-127">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="3a7ad-127">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
- [<span data-ttu-id="3a7ad-128">LINQ to Entities クエリ内の関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="3a7ad-128">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="3a7ad-129">方法: モデル定義関数をオブジェクト メソッドとして呼び出す</span><span class="sxs-lookup"><span data-stu-id="3a7ad-129">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
