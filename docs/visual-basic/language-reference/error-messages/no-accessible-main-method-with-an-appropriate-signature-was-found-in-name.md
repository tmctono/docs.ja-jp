---
title: 正しいシグネチャを持つ、アクセス可能な 'Main' メソッドは、'<name>' に見つかりませんでした。
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: f5053bddf4b9ba791ad6d0733e1dd89c4ded91bd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818359"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="4de16-102">適切なシグネチャを持つアクセス可能な 'Main' メソッドが見つかりませんでした '\<名 >'</span><span class="sxs-lookup"><span data-stu-id="4de16-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="4de16-103">コマンド ライン アプリケーションが必要、`Sub Main`定義します。</span><span class="sxs-lookup"><span data-stu-id="4de16-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="4de16-104">`Main` として宣言する必要があります`Public Shared`クラス、またはとして定義されている場合`Public`モジュールで定義されている場合。</span><span class="sxs-lookup"><span data-stu-id="4de16-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="4de16-105">**エラー ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="4de16-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4de16-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="4de16-106">To correct this error</span></span>  
  
-   <span data-ttu-id="4de16-107">定義、`Public Sub Main`プロジェクト用のプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="4de16-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="4de16-108">として宣言`Shared`クラス内で定義する場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="4de16-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de16-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="4de16-109">See also</span></span>

- [<span data-ttu-id="4de16-110">Visual Basic プログラムの構造</span><span class="sxs-lookup"><span data-stu-id="4de16-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="4de16-111">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4de16-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
