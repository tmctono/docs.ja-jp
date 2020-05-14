---
title: 正しいシグネチャを持つ、アクセス可能な 'Main' メソッドは、'<name>' に見つかりませんでした。
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 559c905d1e2e2de4500771a93d6116f9630011ba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591977"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="01df4-102">正しいシグネチャを持つ、アクセス可能な 'Main' メソッドは、'\<name>' に見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="01df4-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="01df4-103">コマンドライン アプリケーションには `Sub Main` が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="01df4-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="01df4-104">`Main` は、クラスで定義されている場合は `Public Shared` として、またはモジュールで定義されている場合は `Public` として宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01df4-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="01df4-105">**エラー ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="01df4-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01df4-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="01df4-106">To correct this error</span></span>  
  
- <span data-ttu-id="01df4-107">プロジェクトに `Public Sub Main` プロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="01df4-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="01df4-108">それをクラス内で定義する場合、かつその場合にのみ、`Shared` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="01df4-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01df4-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="01df4-109">See also</span></span>

- [<span data-ttu-id="01df4-110">Visual Basic プログラムの構造</span><span class="sxs-lookup"><span data-stu-id="01df4-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="01df4-111">手順</span><span class="sxs-lookup"><span data-stu-id="01df4-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
