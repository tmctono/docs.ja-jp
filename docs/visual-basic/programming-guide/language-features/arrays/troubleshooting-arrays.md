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
ms.openlocfilehash: e633c5a00693f188270b1610abaf2decb656b00a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414596"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="cf260-102">配列のトラブルシューティング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf260-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="cf260-103">ここでは、配列を使用しているときに発生する可能性のある一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf260-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="cf260-104">配列の宣言と初期化のコンパイル エラー</span><span class="sxs-lookup"><span data-stu-id="cf260-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="cf260-105">コンパイル エラーは、配列の宣言、作成、および初期化に関する規則の解釈の誤りが原因で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf260-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="cf260-106">エラーの最も一般的な原因は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cf260-106">The most common causes of errors are the following:</span></span>  
  
- <span data-ttu-id="cf260-107">配列変数宣言で、次元の長さを指定した後に [new 演算子](../../../language-reference/operators/new-operator.md)句を指定した。</span><span class="sxs-lookup"><span data-stu-id="cf260-107">Supplying a [New Operator](../../../language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="cf260-108">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="cf260-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- <span data-ttu-id="cf260-109">ジャグ配列の最上位の配列を超える次元の長さを指定した。</span><span class="sxs-lookup"><span data-stu-id="cf260-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="cf260-110">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="cf260-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- <span data-ttu-id="cf260-111">要素値を指定するときに `New` キーワードを省略した。</span><span class="sxs-lookup"><span data-stu-id="cf260-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="cf260-112">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="cf260-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- <span data-ttu-id="cf260-113">中かっこ (`{}`) を使用せずに `New` 句を指定した。</span><span class="sxs-lookup"><span data-stu-id="cf260-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="cf260-114">次のコード行は、この型の無効な宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="cf260-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="cf260-115">範囲外の配列へのアクセス</span><span class="sxs-lookup"><span data-stu-id="cf260-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="cf260-116">配列を初期化するプロセスでは、各次元に上限と下限が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cf260-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="cf260-117">配列の要素にアクセスする場合は必ず、有効なインデックス (添字) を次元ごとに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf260-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="cf260-118">インデックスのいずれかが下限を下回るか上限を超えていると、<xref:System.IndexOutOfRangeException> 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="cf260-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="cf260-119">このようなエラーはコンパイラでは検出できないため、実行時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cf260-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="cf260-120">境界の特定</span><span class="sxs-lookup"><span data-stu-id="cf260-120">Determining Bounds</span></span>  
 <span data-ttu-id="cf260-121">配列が別のコンポーネントによってコードに渡される場合、たとえばプロシージャの引数として渡される場合、その配列のサイズやその次元の長さはわかりません。</span><span class="sxs-lookup"><span data-stu-id="cf260-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="cf260-122">どの要素でも、要素へのアクセスを試みる場合は必ず、配列のすべての次元の上限を事前に決めておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf260-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="cf260-123">配列が Visual Basic の `New` 句以外の方法で作成された場合、下限は 0 以外の値になる可能性があるため、最も確実なのは下限も決めておくことです。</span><span class="sxs-lookup"><span data-stu-id="cf260-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="cf260-124">次元の指定</span><span class="sxs-lookup"><span data-stu-id="cf260-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="cf260-125">多次元配列の境界を決めるときは、次元を指定する方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cf260-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="cf260-126"><xref:System.Array.GetLowerBound%2A> メソッドと <xref:System.Array.GetUpperBound%2A> メソッドの `dimension` パラメーターは 0 から始まりますが、Visual Basic の <xref:Microsoft.VisualBasic.Information.LBound%2A> 関数と <xref:Microsoft.VisualBasic.Information.UBound%2A> 関数の `Rank` パラメーターは 1 から始まります。</span><span class="sxs-lookup"><span data-stu-id="cf260-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf260-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf260-127">See also</span></span>

- [<span data-ttu-id="cf260-128">配列</span><span class="sxs-lookup"><span data-stu-id="cf260-128">Arrays</span></span>](index.md)
- [<span data-ttu-id="cf260-129">方法: Visual Basic で配列変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="cf260-129">How to: Initialize an Array Variable in Visual Basic</span></span>](how-to-initialize-an-array-variable.md)
