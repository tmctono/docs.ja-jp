---
title: 定義クラスのインスタンスではないオブジェクトのフレンド関数は呼び出せません
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: c18c04470c4c49113e8195b92185326c5c4197c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400849"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="9f1a0-102">定義クラスのインスタンスではないオブジェクトのフレンド関数は呼び出せません</span><span class="sxs-lookup"><span data-stu-id="9f1a0-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="9f1a0-103">クラスの `Friend` プロシージャを呼び出そうとするか、プロセス間またはスレッド間で `Friend` プロパティまたはメソッドにアクセスしようとしました。</span><span class="sxs-lookup"><span data-stu-id="9f1a0-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="9f1a0-104">`Friend` 手順はクラスの外部のモジュールから呼び出せますが、クラスが定義されているプロジェクトの一部です。</span><span class="sxs-lookup"><span data-stu-id="9f1a0-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9f1a0-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="9f1a0-105">To correct this error</span></span>  
  
- <span data-ttu-id="9f1a0-106">クラスが定義されているプロジェクトの一部であるモジュールからプロシージャを呼び出しているか、またはアクセスしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f1a0-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f1a0-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f1a0-107">See also</span></span>

- [<span data-ttu-id="9f1a0-108">Friend</span><span class="sxs-lookup"><span data-stu-id="9f1a0-108">Friend</span></span>](../language-reference/modifiers/friend.md)
