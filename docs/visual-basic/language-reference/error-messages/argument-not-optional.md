---
title: 引数は省略できません。
ms.date: 07/20/2015
f1_keywords:
- vbrID449
ms.assetid: 76e7bcf3-24ed-4cd5-945b-b98f1c76944b
ms.openlocfilehash: 043d126b07838f1a98788021048e5f22e3bc42ed
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353911"
---
# <a name="argument-not-optional-visual-basic"></a><span data-ttu-id="bd137-102">引数は省略できません。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd137-102">Argument not optional (Visual Basic)</span></span>

<span data-ttu-id="bd137-103">引数の数と型は、予期されるものと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd137-103">The number and types of arguments must match those expected.</span></span> <span data-ttu-id="bd137-104">引数の数が正しくないか、省略された引数が省略可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="bd137-104">Either there is an incorrect number of arguments, or an omitted argument is not optional.</span></span> <span data-ttu-id="bd137-105">引数は、プロシージャの定義で `Optional` と宣言されている場合にのみ、ユーザー定義プロシージャの呼び出しから省略できます。</span><span class="sxs-lookup"><span data-stu-id="bd137-105">An argument can only be omitted from a call to a user-defined procedure if it was declared `Optional` in the procedure definition.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bd137-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="bd137-106">To correct this error</span></span>  
  
1. <span data-ttu-id="bd137-107">必要なすべての引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd137-107">Supply all necessary arguments.</span></span>  
  
2. <span data-ttu-id="bd137-108">省略された引数が省略可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd137-108">Make sure omitted arguments are optional.</span></span> <span data-ttu-id="bd137-109">そうでない場合は、呼び出しに引数を指定するか、定義内でパラメーター `Optional` を宣言します。</span><span class="sxs-lookup"><span data-stu-id="bd137-109">If they are not, either supply the argument in the call, or declare the parameter `Optional` in the definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd137-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd137-110">See also</span></span>

- [<span data-ttu-id="bd137-111">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="bd137-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
