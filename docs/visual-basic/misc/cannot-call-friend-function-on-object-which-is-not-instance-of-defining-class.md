---
title: 定義クラスのインスタンスではないオブジェクトのフレンド関数は呼び出せません
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: fe95f80d42fc12ab2829db899fe295e32f358db6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059809"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="ed6f4-102">定義クラスのインスタンスではないオブジェクトのフレンド関数は呼び出せません</span><span class="sxs-lookup"><span data-stu-id="ed6f4-102">Cannot call friend function on object which is not an instance of defining class</span></span>

<span data-ttu-id="ed6f4-103">クラスの `Friend` プロシージャを呼び出そうとするか、プロセス間またはスレッド間で `Friend` プロパティまたはメソッドにアクセスしようとしました。</span><span class="sxs-lookup"><span data-stu-id="ed6f4-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="ed6f4-104">`Friend` 手順はクラスの外部のモジュールから呼び出せますが、クラスが定義されているプロジェクトの一部です。</span><span class="sxs-lookup"><span data-stu-id="ed6f4-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed6f4-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="ed6f4-105">To correct this error</span></span>  
  
- <span data-ttu-id="ed6f4-106">クラスが定義されているプロジェクトの一部であるモジュールからプロシージャを呼び出しているか、またはアクセスしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed6f4-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6f4-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed6f4-107">See also</span></span>

- [<span data-ttu-id="ed6f4-108">Friend</span><span class="sxs-lookup"><span data-stu-id="ed6f4-108">Friend</span></span>](../language-reference/modifiers/friend.md)
