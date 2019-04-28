---
title: DLL を正しく呼び出せません。
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: f7b0c3a6edbe0b950195306fa66287ff9b209bfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935279"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="fa27f-102">DLL を正しく呼び出せません。</span><span class="sxs-lookup"><span data-stu-id="fa27f-102">Bad DLL calling convention</span></span>
<span data-ttu-id="fa27f-103">ダイナミック リンク ライブラリ (DLL) に渡される引数が、ルーチンで想定されているものを正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa27f-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="fa27f-104">呼び出し規則は、数、種類、および引数の順序で処理します。</span><span class="sxs-lookup"><span data-stu-id="fa27f-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="fa27f-105">プログラムを無効な型または引数の数が渡される DLL にルーチンを呼び出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa27f-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fa27f-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="fa27f-106">To correct this error</span></span>  
  
1. <span data-ttu-id="fa27f-107">すべての引数の型に同意を呼び出すルーチンの宣言で指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa27f-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2. <span data-ttu-id="fa27f-108">同じ数の呼び出しの対象とするルーチンの宣言に示されている引数を渡していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa27f-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3. <span data-ttu-id="fa27f-109">DLL 内のルーチンは、値によって引数が必要ですが場合に、必ず`ByVal`ルーチンの宣言でこれらの引数が指定されています。</span><span class="sxs-lookup"><span data-stu-id="fa27f-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa27f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa27f-110">See also</span></span>

- [<span data-ttu-id="fa27f-111">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="fa27f-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="fa27f-112">Call ステートメント</span><span class="sxs-lookup"><span data-stu-id="fa27f-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)
- [<span data-ttu-id="fa27f-113">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="fa27f-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
