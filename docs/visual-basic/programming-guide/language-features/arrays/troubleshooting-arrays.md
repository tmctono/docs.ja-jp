---
title: 配列のトラブルシューティング
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 3c50c68c2a39aa04cff2dd43b5dfde709aec290f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349065"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="a8b47-102">配列のトラブルシューティング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8b47-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="a8b47-103">このページでは、配列を使用するときに発生する可能性のある一般的な問題をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="a8b47-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="a8b47-104">配列の宣言と初期化に関するコンパイルエラー</span><span class="sxs-lookup"><span data-stu-id="a8b47-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="a8b47-105">コンパイルエラーは、配列の宣言、作成、および初期化に関する規則の誤解から生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8b47-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="a8b47-106">エラーの最も一般的な原因は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a8b47-106">The most common causes of errors are the following:</span></span>  
  
- <span data-ttu-id="a8b47-107">配列変数宣言で次元の長さを指定した後に、[New 演算子](../../../../visual-basic/language-reference/operators/new-operator.md) 句を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b47-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="a8b47-108">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="a8b47-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- <span data-ttu-id="a8b47-109">ジャグ配列の最上位レベル配列を超える次元の長さを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b47-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="a8b47-110">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="a8b47-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- <span data-ttu-id="a8b47-111">要素の値を指定するときに、`New` キーワードを省略します。</span><span class="sxs-lookup"><span data-stu-id="a8b47-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="a8b47-112">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="a8b47-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- <span data-ttu-id="a8b47-113">中かっこ (`{}`) のない `New` 句を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b47-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="a8b47-114">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="a8b47-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="a8b47-115">配列へのアクセス (範囲外)</span><span class="sxs-lookup"><span data-stu-id="a8b47-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="a8b47-116">配列を初期化するプロセスでは、各次元に上限と下限が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a8b47-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="a8b47-117">配列の要素へのすべてのアクセスでは、各次元に有効なインデックス (添字) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b47-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="a8b47-118">インデックスが下限を下回るか上限を超えている場合、<xref:System.IndexOutOfRangeException> 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="a8b47-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="a8b47-119">コンパイラはこのようなエラーを検出できないため、実行時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a8b47-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="a8b47-120">範囲の決定</span><span class="sxs-lookup"><span data-stu-id="a8b47-120">Determining Bounds</span></span>  
 <span data-ttu-id="a8b47-121">別のコンポーネントがコードに配列を渡す場合 (たとえば、プロシージャの引数として)、その配列のサイズや次元の長さはわかりません。</span><span class="sxs-lookup"><span data-stu-id="a8b47-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="a8b47-122">すべての要素にアクセスする前に、配列の各次元の上限を常に決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b47-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="a8b47-123">配列が Visual Basic `New` 句以外の何らかの方法で作成されている場合、下限は0以外の値になる可能性があり、下限が下限であるかどうかを判断するのは安全です。</span><span class="sxs-lookup"><span data-stu-id="a8b47-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="a8b47-124">ディメンションの指定</span><span class="sxs-lookup"><span data-stu-id="a8b47-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="a8b47-125">多次元配列の範囲を決定するときは、ディメンションをどのように指定するかを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="a8b47-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="a8b47-126"><xref:System.Array.GetLowerBound%2A> メソッドと <xref:System.Array.GetUpperBound%2A> メソッドの `dimension` パラメーターは0から始まるものですが、Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> 関数と <xref:Microsoft.VisualBasic.Information.UBound%2A> 関数の `Rank` パラメーターは1から始まるものです。</span><span class="sxs-lookup"><span data-stu-id="a8b47-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b47-127">参照</span><span class="sxs-lookup"><span data-stu-id="a8b47-127">See also</span></span>

- [<span data-ttu-id="a8b47-128">配列</span><span class="sxs-lookup"><span data-stu-id="a8b47-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a8b47-129">方法: Visual Basic で配列変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="a8b47-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
