---
title: "'<keyword>' は、インスタンス メソッド内でのみ有効です。"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af436b8fd57ff0d2747c766a64af175760931009
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873897"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="d8d41-102">'\<keyword>' は、インスタンス メソッド内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d8d41-102">'\<keyword>' is valid only within an instance method</span></span>

<span data-ttu-id="d8d41-103">`Me`、`MyClass`、および `MyBase` キーワードは、特定のクラス インスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="d8d41-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="d8d41-104">それらを共有の `Function` または `Sub` プロシージャ内で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8d41-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="d8d41-105">**エラー ID:** BC30043</span><span class="sxs-lookup"><span data-stu-id="d8d41-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8d41-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d8d41-106">To correct this error</span></span>  
  
- <span data-ttu-id="d8d41-107">プロシージャからキーワードを削除するか、プロシージャ宣言から `Shared` キーワードを削除します。</span><span class="sxs-lookup"><span data-stu-id="d8d41-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d41-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8d41-108">See also</span></span>

- [<span data-ttu-id="d8d41-109">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="d8d41-109">Object Variable Assignment</span></span>](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="d8d41-110">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="d8d41-110">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="d8d41-111">継承の基本</span><span class="sxs-lookup"><span data-stu-id="d8d41-111">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
