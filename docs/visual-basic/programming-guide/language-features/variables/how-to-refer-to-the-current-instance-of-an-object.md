---
title: '方法: オブジェクトの現在のインスタンスを参照する'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 62b22a54904a45380052d3d81d9415517d4f8d3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346882"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="77caf-102">方法: オブジェクトの現在のインスタンスを参照する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77caf-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="77caf-103">The *current instance* of an object is the instance in which the code is currently executing.</span><span class="sxs-lookup"><span data-stu-id="77caf-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="77caf-104">You use the `Me` keyword to refer to the current instance.</span><span class="sxs-lookup"><span data-stu-id="77caf-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="77caf-105">To refer to the current instance</span><span class="sxs-lookup"><span data-stu-id="77caf-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="77caf-106">Use the `Me` keyword where you would normally use the name of an object variable.</span><span class="sxs-lookup"><span data-stu-id="77caf-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="77caf-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span><span class="sxs-lookup"><span data-stu-id="77caf-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="77caf-108">`Me` always refers to the current instance.</span><span class="sxs-lookup"><span data-stu-id="77caf-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77caf-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="77caf-109">See also</span></span>

- [<span data-ttu-id="77caf-110">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="77caf-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="77caf-111">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="77caf-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="77caf-112">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="77caf-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
