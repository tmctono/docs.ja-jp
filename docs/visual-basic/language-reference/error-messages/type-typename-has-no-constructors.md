---
title: 型 '<typename>' にはコンストラクターがありません。
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 8fc173182d062c80ffde15b1e7210644d37f8f66
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875110"
---
# <a name="type-typename-has-no-constructors"></a><span data-ttu-id="1b14e-102">型 '\<typename>' にはコンストラクターがありません。</span><span class="sxs-lookup"><span data-stu-id="1b14e-102">Type '\<typename>' has no constructors</span></span>

<span data-ttu-id="1b14e-103">型が `Sub New()` の呼び出しをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="1b14e-103">A type does not support a call to `Sub New()`.</span></span> <span data-ttu-id="1b14e-104">コンパイラまたはバイナリ ファイルが破損していることが原因の 1 つとして考えられます。</span><span class="sxs-lookup"><span data-stu-id="1b14e-104">One possible cause is a corrupted compiler or binary file.</span></span>  
  
 <span data-ttu-id="1b14e-105">**エラー ID:** BC30251</span><span class="sxs-lookup"><span data-stu-id="1b14e-105">**Error ID:** BC30251</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b14e-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1b14e-106">To correct this error</span></span>  
  
1. <span data-ttu-id="1b14e-107">型が別のプロジェクトまたは参照ファイル内にある場合は、プロジェクトまたはファイルを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="1b14e-107">If the type is in a different project or in a referenced file, reinstall the project or file.</span></span>  
  
2. <span data-ttu-id="1b14e-108">型が同じプロジェクト内にある場合は、型を含むアセンブリを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1b14e-108">If the type is in the same project, recompile the assembly containing the type.</span></span>  
  
3. <span data-ttu-id="1b14e-109">エラーがまだ発生する場合は、Visual Basic コンパイラを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="1b14e-109">If the error recurs, reinstall the Visual Basic compiler.</span></span>  
  
4. <span data-ttu-id="1b14e-110">エラーが続く場合は、状況に関する情報を収集し、マイクロソフト プロダクト サポート サービスに通知してください。</span><span class="sxs-lookup"><span data-stu-id="1b14e-110">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b14e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b14e-111">See also</span></span>

- [<span data-ttu-id="1b14e-112">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="1b14e-112">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="1b14e-113">ご意見</span><span class="sxs-lookup"><span data-stu-id="1b14e-113">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
