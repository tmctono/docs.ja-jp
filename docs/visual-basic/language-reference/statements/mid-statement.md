---
title: Mid ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: 212ce1f06a01c39acbce43d8d069dae3526b1b4d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963552"
---
# <a name="mid-statement"></a><span data-ttu-id="58f0e-102">Mid ステートメント</span><span class="sxs-lookup"><span data-stu-id="58f0e-102">Mid Statement</span></span>
<span data-ttu-id="58f0e-103">`String`変数内の指定された数の文字を別の文字列の文字に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="58f0e-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f0e-104">構文</span><span class="sxs-lookup"><span data-stu-id="58f0e-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="58f0e-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="58f0e-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="58f0e-106">必須。</span><span class="sxs-lookup"><span data-stu-id="58f0e-106">Required.</span></span> <span data-ttu-id="58f0e-107">変更する`String`変数の名前。</span><span class="sxs-lookup"><span data-stu-id="58f0e-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="58f0e-108">必須。</span><span class="sxs-lookup"><span data-stu-id="58f0e-108">Required.</span></span> <span data-ttu-id="58f0e-109">`Integer`条件.</span><span class="sxs-lookup"><span data-stu-id="58f0e-109">`Integer` expression.</span></span> <span data-ttu-id="58f0e-110">テキストの置換`Target`を開始する位置の文字位置。</span><span class="sxs-lookup"><span data-stu-id="58f0e-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="58f0e-111">`Start`1から始まるインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="58f0e-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="58f0e-112">任意。</span><span class="sxs-lookup"><span data-stu-id="58f0e-112">Optional.</span></span> <span data-ttu-id="58f0e-113">`Integer`条件.</span><span class="sxs-lookup"><span data-stu-id="58f0e-113">`Integer` expression.</span></span> <span data-ttu-id="58f0e-114">置換する文字数。</span><span class="sxs-lookup"><span data-stu-id="58f0e-114">Number of characters to replace.</span></span> <span data-ttu-id="58f0e-115">省略した場合`String`は、すべてが使用されます。</span><span class="sxs-lookup"><span data-stu-id="58f0e-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="58f0e-116">必須。</span><span class="sxs-lookup"><span data-stu-id="58f0e-116">Required.</span></span> <span data-ttu-id="58f0e-117">`String`の`Target`一部を置換する式。</span><span class="sxs-lookup"><span data-stu-id="58f0e-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="58f0e-118">例外</span><span class="sxs-lookup"><span data-stu-id="58f0e-118">Exceptions</span></span>  
  
|<span data-ttu-id="58f0e-119">例外の型</span><span class="sxs-lookup"><span data-stu-id="58f0e-119">Exception type</span></span>|<span data-ttu-id="58f0e-120">条件</span><span class="sxs-lookup"><span data-stu-id="58f0e-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="58f0e-121">`Start`< = 0 また`Length`は < 0 です。</span><span class="sxs-lookup"><span data-stu-id="58f0e-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58f0e-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="58f0e-122">Remarks</span></span>  
 <span data-ttu-id="58f0e-123">置換される文字数は、常にの文字`Target`数以下です。</span><span class="sxs-lookup"><span data-stu-id="58f0e-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="58f0e-124">Visual Basic には<xref:Microsoft.VisualBasic.Strings.Mid%2A> 、関数`Mid`とステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="58f0e-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="58f0e-125">これらの要素は、どちらも文字列内の指定された文字数`Mid`に対して動作します`Mid`が、関数は、ステートメントが文字を置換する間、文字を返します。</span><span class="sxs-lookup"><span data-stu-id="58f0e-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="58f0e-126">詳細については、「 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58f0e-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58f0e-127">以前のバージョンの Visual Basic のステートメントでは、文字ではなく、部分文字列がバイト単位で置き換えられます。`MidB`</span><span class="sxs-lookup"><span data-stu-id="58f0e-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="58f0e-128">これは主に、2バイト文字セット (DBCS) アプリケーションで文字列を変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="58f0e-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="58f0e-129">すべての Visual Basic 文字列は Unicode `MidB`形式であり、サポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="58f0e-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58f0e-130">例</span><span class="sxs-lookup"><span data-stu-id="58f0e-130">Example</span></span>  
 <span data-ttu-id="58f0e-131">この例では`Mid` 、ステートメントを使用して、文字列変数内の指定された数の文字を別の文字列の文字に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="58f0e-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="58f0e-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="58f0e-132">Requirements</span></span>  
 <span data-ttu-id="58f0e-133">**名前空間:** [Microsoft. Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="58f0e-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="58f0e-134">**モジュール:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="58f0e-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="58f0e-135">**組み立て**Visual Basic ランタイム ライブラリ (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="58f0e-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f0e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="58f0e-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="58f0e-137">文字列</span><span class="sxs-lookup"><span data-stu-id="58f0e-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="58f0e-138">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="58f0e-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
