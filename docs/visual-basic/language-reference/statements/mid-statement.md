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
ms.openlocfilehash: ea22af2eb896542bfc329e087101608e08c45107
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581476"
---
# <a name="mid-statement"></a><span data-ttu-id="a671d-102">Mid ステートメント</span><span class="sxs-lookup"><span data-stu-id="a671d-102">Mid Statement</span></span>
<span data-ttu-id="a671d-103">@No__t_0 変数内の指定された数の文字を、別の文字列の文字に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a671d-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a671d-104">構文</span><span class="sxs-lookup"><span data-stu-id="a671d-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="a671d-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="a671d-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="a671d-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="a671d-106">Required.</span></span> <span data-ttu-id="a671d-107">変更する `String` 変数の名前。</span><span class="sxs-lookup"><span data-stu-id="a671d-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="a671d-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="a671d-108">Required.</span></span> <span data-ttu-id="a671d-109">`Integer` 式です。</span><span class="sxs-lookup"><span data-stu-id="a671d-109">`Integer` expression.</span></span> <span data-ttu-id="a671d-110">@No__t_0 の文字位置。テキストの置換が開始されます。</span><span class="sxs-lookup"><span data-stu-id="a671d-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="a671d-111">`Start` は、1から始まるインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a671d-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="a671d-112">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a671d-112">Optional.</span></span> <span data-ttu-id="a671d-113">`Integer` 式です。</span><span class="sxs-lookup"><span data-stu-id="a671d-113">`Integer` expression.</span></span> <span data-ttu-id="a671d-114">置換する文字数。</span><span class="sxs-lookup"><span data-stu-id="a671d-114">Number of characters to replace.</span></span> <span data-ttu-id="a671d-115">省略した場合、すべての `String` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a671d-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="a671d-116">必須です。</span><span class="sxs-lookup"><span data-stu-id="a671d-116">Required.</span></span> <span data-ttu-id="a671d-117">`Target` の一部を置き換える `String` 式。</span><span class="sxs-lookup"><span data-stu-id="a671d-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="a671d-118">例外</span><span class="sxs-lookup"><span data-stu-id="a671d-118">Exceptions</span></span>  
  
|<span data-ttu-id="a671d-119">例外の種類</span><span class="sxs-lookup"><span data-stu-id="a671d-119">Exception type</span></span>|<span data-ttu-id="a671d-120">条件</span><span class="sxs-lookup"><span data-stu-id="a671d-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="a671d-121">`Start` < = 0 または `Length` < 0 です。</span><span class="sxs-lookup"><span data-stu-id="a671d-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a671d-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="a671d-122">Remarks</span></span>  
 <span data-ttu-id="a671d-123">置換される文字数は、常に `Target` の文字数以下です。</span><span class="sxs-lookup"><span data-stu-id="a671d-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="a671d-124">Visual Basic には <xref:Microsoft.VisualBasic.Strings.Mid%2A> 関数と `Mid` ステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="a671d-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="a671d-125">これらの要素は、どちらも文字列内の指定された文字数に対して動作しますが、`Mid` ステートメントによって文字が置き換えられる間、`Mid` 関数は文字を返します。</span><span class="sxs-lookup"><span data-stu-id="a671d-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="a671d-126">詳細については、「<xref:Microsoft.VisualBasic.Strings.Mid%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a671d-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a671d-127">以前のバージョンの Visual Basic の `MidB` ステートメントは、文字ではなく、バイト単位の部分文字列を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a671d-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="a671d-128">これは主に、2バイト文字セット (DBCS) アプリケーションで文字列を変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a671d-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="a671d-129">すべての Visual Basic 文字列は Unicode 形式であり、`MidB` はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a671d-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a671d-130">例</span><span class="sxs-lookup"><span data-stu-id="a671d-130">Example</span></span>  
 <span data-ttu-id="a671d-131">この例では、`Mid` ステートメントを使用して、文字列変数内の指定された数の文字を別の文字列の文字に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a671d-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="a671d-132">［要件］</span><span class="sxs-lookup"><span data-stu-id="a671d-132">Requirements</span></span>  
 <span data-ttu-id="a671d-133">**名前空間:** [Microsoft. visual basic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="a671d-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="a671d-134">**モジュール:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="a671d-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="a671d-135">**アセンブリ:** Visual Basic ランタイムライブラリ (Microsoft... .dll)</span><span class="sxs-lookup"><span data-stu-id="a671d-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a671d-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a671d-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="a671d-137">文字列</span><span class="sxs-lookup"><span data-stu-id="a671d-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="a671d-138">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="a671d-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
