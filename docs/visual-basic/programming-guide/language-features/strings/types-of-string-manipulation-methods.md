---
title: Visual Basic における文字列操作メソッドの種類
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 44eb101ebdfeb316958a659107190ef1fc84df44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938269"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="3d6b5-102">Visual Basic における文字列操作メソッドの種類</span><span class="sxs-lookup"><span data-stu-id="3d6b5-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="3d6b5-103">いくつかの方法を分析し、文字列の操作があります。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="3d6b5-104">Visual Basic 言語の一部である一部のメソッドと他のユーザーに固有では、`String`クラス。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="3d6b5-105">Visual Basic 言語と .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3d6b5-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="3d6b5-106">Visual Basic のメソッドは、言語固有の関数として使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="3d6b5-107">付けず、コードで使用することです。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="3d6b5-108">次の例は、Visual Basic の文字列操作コマンドの一般的な使用を示しています。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="3d6b5-109">この例で、`Mid`関数で直接操作を実行する`aString`に値が割り当てられます`bString`します。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="3d6b5-110">Visual Basic の文字列操作メソッドの一覧は、次を参照してください。[文字列操作の概要](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="3d6b5-111">共有メソッドとインスタンス メソッド</span><span class="sxs-lookup"><span data-stu-id="3d6b5-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="3d6b5-112">メソッドを使って、文字列を操作することも、`String`クラス。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="3d6b5-113">内のメソッドの 2 種類があります`String`:*共有*メソッドと*インスタンス*メソッド。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="3d6b5-114">共有メソッド</span><span class="sxs-lookup"><span data-stu-id="3d6b5-114">Shared Methods</span></span>  
 <span data-ttu-id="3d6b5-115">共有メソッドに由来するメソッド、`String`クラス自体と、操作するには、そのクラスのインスタンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="3d6b5-116">これらのメソッドは、クラスの名前で修飾することができます (`String`) のインスタンスではなく、`String`クラス。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="3d6b5-117">例:</span><span class="sxs-lookup"><span data-stu-id="3d6b5-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="3d6b5-118">上記の例では、<xref:System.String.Copy%2A?displayProperty=nameWithType>メソッドは静的メソッドを式に対して機能することが指定され、その結果の値を割り当てます`bString`します。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="3d6b5-119">インスタンス メソッド</span><span class="sxs-lookup"><span data-stu-id="3d6b5-119">Instance Methods</span></span>  
 <span data-ttu-id="3d6b5-120">インスタンス メソッド、の特定のインスタンスからこれに対し、語幹`String`インスタンス名で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="3d6b5-121">例:</span><span class="sxs-lookup"><span data-stu-id="3d6b5-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="3d6b5-122">この例で、<xref:System.String.Substring%2A?displayProperty=nameWithType>メソッドは、メソッドのインスタンスの`String`(つまり、 `aString`)。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="3d6b5-123">操作の実行`aString`にその値を割り当てます`bString`します。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="3d6b5-124">詳細については、ドキュメントを参照して、<xref:System.String>クラス。</span><span class="sxs-lookup"><span data-stu-id="3d6b5-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6b5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d6b5-125">See also</span></span>

- [<span data-ttu-id="3d6b5-126">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="3d6b5-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
