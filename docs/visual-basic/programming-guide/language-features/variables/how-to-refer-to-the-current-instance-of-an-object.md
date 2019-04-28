---
title: '方法: オブジェクト (Visual Basic) の現在のインスタンスを参照してください。'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 3c44748798d5ed554fc9fbded9c3a4d981a66d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769032"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="d6f20-102">方法: オブジェクト (Visual Basic) の現在のインスタンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6f20-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="d6f20-103">*現在インスタンス*オブジェクトが現在のコードが実行されているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="d6f20-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="d6f20-104">使用する、`Me`キーワードを現在のインスタンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6f20-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="d6f20-105">現在のインスタンスを参照するには</span><span class="sxs-lookup"><span data-stu-id="d6f20-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="d6f20-106">使用して、`Me`オブジェクト変数の名前を通常使用するキーワード。</span><span class="sxs-lookup"><span data-stu-id="d6f20-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="d6f20-107">ただし`Me`オブジェクトと同様に動作変数、宣言またはできないものを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d6f20-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="d6f20-108">`Me` 常に現在のインスタンスを指します。</span><span class="sxs-lookup"><span data-stu-id="d6f20-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f20-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6f20-109">See also</span></span>

- [<span data-ttu-id="d6f20-110">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="d6f20-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="d6f20-111">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="d6f20-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="d6f20-112">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="d6f20-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
