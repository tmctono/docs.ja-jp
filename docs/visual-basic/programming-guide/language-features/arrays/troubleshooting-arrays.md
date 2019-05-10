---
title: 配列のトラブルシューティング (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 69d5294eacc59718adb1b0a226594d2cf69273f5
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913462"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="92872-102">配列のトラブルシューティング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92872-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="92872-103">このページには、配列を使用する場合に発生する可能性がある一般的な問題が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="92872-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="92872-104">コンパイル エラーを宣言して、配列の初期化</span><span class="sxs-lookup"><span data-stu-id="92872-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="92872-105">宣言、作成、および配列の初期化の規則の誤解からコンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="92872-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="92872-106">エラーの最も一般的な原因は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="92872-106">The most common causes of errors are the following:</span></span>  
  
- <span data-ttu-id="92872-107">指定する、 [New 演算子](../../../../visual-basic/language-reference/operators/new-operator.md)配列変数の宣言に次元の長さを指定した後の句。</span><span class="sxs-lookup"><span data-stu-id="92872-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="92872-108">次のコード行では、この型の無効な宣言を表示します。</span><span class="sxs-lookup"><span data-stu-id="92872-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- <span data-ttu-id="92872-109">ジャグ配列の最上位の配列の次元の長さを指定します。</span><span class="sxs-lookup"><span data-stu-id="92872-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="92872-110">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="92872-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- <span data-ttu-id="92872-111">省略すると、`New`キーワード要素の値を指定する場合。</span><span class="sxs-lookup"><span data-stu-id="92872-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="92872-112">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="92872-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- <span data-ttu-id="92872-113">指定する、`New`中かっこのない句 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="92872-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="92872-114">次のコード行では、この型の無効な宣言を表示します。</span><span class="sxs-lookup"><span data-stu-id="92872-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="92872-115">範囲外の配列へのアクセス</span><span class="sxs-lookup"><span data-stu-id="92872-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="92872-116">配列の初期化中のプロセスは、各ディメンションを上限と下限の境界を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="92872-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="92872-117">配列の要素へのすべてのアクセスには、有効なインデックス、またはすべてのディメンションの添字を指定します。</span><span class="sxs-lookup"><span data-stu-id="92872-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="92872-118">任意のインデックスが、上限の上または下の下限の境界の場合、<xref:System.IndexOutOfRangeException>例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="92872-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="92872-119">コンパイラは、実行時にエラーが発生したため、このようなエラーを検出できません。</span><span class="sxs-lookup"><span data-stu-id="92872-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="92872-120">範囲の確認</span><span class="sxs-lookup"><span data-stu-id="92872-120">Determining Bounds</span></span>  
 <span data-ttu-id="92872-121">場合は、コードに別のコンポーネントが配列を渡すと、たとえば、プロシージャの引数としてわからないその配列のサイズまたはその次元の長さ。</span><span class="sxs-lookup"><span data-stu-id="92872-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="92872-122">任意の要素にアクセスしようとする前に常に配列のすべての次元の上限の境界を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92872-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="92872-123">Visual Basic 以外の手段で配列が作成された場合`New`句では、下限の境界では、0 でない可能性がありもその下限の境界を決定するおくと安心になります。</span><span class="sxs-lookup"><span data-stu-id="92872-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="92872-124">ディメンションを指定します。</span><span class="sxs-lookup"><span data-stu-id="92872-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="92872-125">多次元配列の境界を決定する際に注意して、ディメンションを指定する方法。</span><span class="sxs-lookup"><span data-stu-id="92872-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="92872-126">`dimension`のパラメーター、<xref:System.Array.GetLowerBound%2A>と<xref:System.Array.GetUpperBound%2A>メソッドは、中に、0 から始まる、 `Rank` Visual Basic のパラメーター<xref:Microsoft.VisualBasic.Information.LBound%2A>と<xref:Microsoft.VisualBasic.Information.UBound%2A>関数は、1 から始まります。</span><span class="sxs-lookup"><span data-stu-id="92872-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92872-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="92872-127">See also</span></span>

- [<span data-ttu-id="92872-128">配列</span><span class="sxs-lookup"><span data-stu-id="92872-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="92872-129">方法: Visual Basic で配列変数を初期化します。</span><span class="sxs-lookup"><span data-stu-id="92872-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
