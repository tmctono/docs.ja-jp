---
title: 文字列操作メソッドの種類
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: a02278abfb71efb2f31f239a89a22ad1c8ee7a18
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346270"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="0efc6-102">Visual Basic における文字列操作メソッドの種類</span><span class="sxs-lookup"><span data-stu-id="0efc6-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="0efc6-103">文字列を分析して操作するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0efc6-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="0efc6-104">一部のメソッドは Visual Basic 言語の一部であり、`String` クラスに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="0efc6-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="0efc6-105">Visual Basic 言語と .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0efc6-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="0efc6-106">Visual Basic メソッドは、言語の固有の関数として使用されます。</span><span class="sxs-lookup"><span data-stu-id="0efc6-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="0efc6-107">これらは、コード内で修飾なしで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0efc6-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="0efc6-108">次の例は、Visual Basic 文字列操作コマンドの一般的な使用法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0efc6-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="0efc6-109">この例では、`Mid` 関数が `aString` に対して直接操作を実行し `bString`に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="0efc6-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="0efc6-110">Visual Basic 文字列操作メソッドの一覧については、「[文字列操作の概要](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0efc6-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="0efc6-111">共有メソッドとインスタンスメソッド</span><span class="sxs-lookup"><span data-stu-id="0efc6-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="0efc6-112">`String` クラスのメソッドを使用して、文字列を操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="0efc6-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="0efc6-113">`String`には、*共有*メソッドと*インスタンス*メソッドという2種類のメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="0efc6-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="0efc6-114">共有メソッド</span><span class="sxs-lookup"><span data-stu-id="0efc6-114">Shared Methods</span></span>  
 <span data-ttu-id="0efc6-115">共有メソッドは、`String` クラス自体からのメソッドであり、そのクラスのインスタンスが動作するためには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0efc6-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="0efc6-116">これらのメソッドは、`String` クラスのインスタンスではなく、クラスの名前 (`String`) で修飾できます。</span><span class="sxs-lookup"><span data-stu-id="0efc6-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="0efc6-117">例 :</span><span class="sxs-lookup"><span data-stu-id="0efc6-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="0efc6-118">前の例では、<xref:System.String.Copy%2A?displayProperty=nameWithType> メソッドは静的メソッドです。このメソッドは、指定された式に対して動作し、結果として得られる値を `bString`に代入します。</span><span class="sxs-lookup"><span data-stu-id="0efc6-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="0efc6-119">インスタンスメソッド</span><span class="sxs-lookup"><span data-stu-id="0efc6-119">Instance Methods</span></span>  
 <span data-ttu-id="0efc6-120">これに対して、インスタンスメソッドは、`String` の特定のインスタンスからのものであり、インスタンス名で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0efc6-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="0efc6-121">例 :</span><span class="sxs-lookup"><span data-stu-id="0efc6-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="0efc6-122">この例では、<xref:System.String.Substring%2A?displayProperty=nameWithType> メソッドは、`String` のインスタンス (つまり、`aString`) のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="0efc6-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="0efc6-123">`aString` に対して操作を実行し、その値を `bString`に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0efc6-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="0efc6-124">詳細については、<xref:System.String> クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0efc6-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0efc6-125">参照</span><span class="sxs-lookup"><span data-stu-id="0efc6-125">See also</span></span>

- [<span data-ttu-id="0efc6-126">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="0efc6-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
