---
title: '方法: クエリを使用してモデル定義関数を呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: 33f26896dd0d4ff08beb4a011fa6bd468cba7207
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250756"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="ca0f2-102">方法: クエリを使用してモデル定義関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="ca0f2-102">How to: Call Model-Defined Functions in Queries</span></span>
<span data-ttu-id="ca0f2-103">このトピックでは、LINQ to Entities クエリ内から、概念モデルで定義されている関数を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-103">This topic describes how to call functions that are defined in the conceptual model from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="ca0f2-104">次の手順では、LINQ to Entities クエリ内からモデル定義関数を呼び出す方法の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-104">The procedure below provides a high-level outline for calling a model-defined function from within a LINQ to Entities query.</span></span> <span data-ttu-id="ca0f2-105">各手順の詳しい説明は、その後の例で示します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="ca0f2-106">この手順では、関数を概念モデルで定義済みであると想定します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="ca0f2-107">詳細については、「[方法 :概念モデル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))でカスタム関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="ca0f2-108">概念モデルで定義された関数を呼び出すには</span><span class="sxs-lookup"><span data-stu-id="ca0f2-108">To call a function defined in the conceptual model</span></span>  
  
1. <span data-ttu-id="ca0f2-109">概念モデルで定義された関数にマップされているアプリケーションに、共通言語ランタイム (CLR) メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="ca0f2-110">メソッドをマップするには、ユーザーが <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> をメソッドに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="ca0f2-111">属性の <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> パラメーターと <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> パラメーターが、それぞれ概念モデルの名前空間名と関数名であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="ca0f2-112">LINQ の関数名解決では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2. <span data-ttu-id="ca0f2-113">LINQ to Entities クエリから関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-113">Call the function in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca0f2-114">例</span><span class="sxs-lookup"><span data-stu-id="ca0f2-114">Example</span></span>  
 <span data-ttu-id="ca0f2-115">次の例は、概念モデルで定義されている関数を LINQ to Entities クエリ内から呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a LINQ to Entities query.</span></span> <span data-ttu-id="ca0f2-116">この例では、School モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-116">The example uses the School model.</span></span> <span data-ttu-id="ca0f2-117">School モデルの詳細については、「 [School サンプルデータベースの作成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))」および「 [school .Edmx ファイルの生成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-117">For information about the School model, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>  
  
 <span data-ttu-id="ca0f2-118">次の概念モデル関数は、あるインストラクターが雇用されてから経過した年数を返します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="ca0f2-119">関数を概念モデルに追加する方法については[、「方法:概念モデル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))でカスタム関数を定義します。)</span><span class="sxs-lookup"><span data-stu-id="ca0f2-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="ca0f2-120">例</span><span class="sxs-lookup"><span data-stu-id="ca0f2-120">Example</span></span>  
 <span data-ttu-id="ca0f2-121">次に、次のメソッドをアプリケーションに追加し、<xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> を使用して概念モデル関数にマップします。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="ca0f2-122">例</span><span class="sxs-lookup"><span data-stu-id="ca0f2-122">Example</span></span>  
 <span data-ttu-id="ca0f2-123">これで、LINQ to Entities クエリ内から概念モデル関数を呼び出すことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-123">Now you can call the conceptual model function from within a LINQ to Entities query.</span></span> <span data-ttu-id="ca0f2-124">次のコードは、雇用年数が 10 年を超えるすべてのインストラクターを表示するメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ca0f2-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ca0f2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca0f2-125">See also</span></span>

- <span data-ttu-id="ca0f2-126">[.edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ca0f2-126">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="ca0f2-127">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="ca0f2-127">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="ca0f2-128">LINQ to Entities クエリ内の関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="ca0f2-128">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="ca0f2-129">方法: モデル定義関数をオブジェクトメソッドとして呼び出す</span><span class="sxs-lookup"><span data-stu-id="ca0f2-129">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)
