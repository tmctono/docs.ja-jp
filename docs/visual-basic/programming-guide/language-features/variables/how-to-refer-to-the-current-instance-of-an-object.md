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
ms.openlocfilehash: 43bfd54592fb1d26cbf7f268b7e098e01e3745d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410426"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="d3e4d-102">方法: オブジェクトの現在のインスタンスを参照する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3e4d-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="d3e4d-103">オブジェクトの "*現在のインスタンス*" は、コードが現在実行されているインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d3e4d-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="d3e4d-104">現在のインスタンスを参照するには、`Me` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3e4d-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="d3e4d-105">現在のインスタンスを参照するには</span><span class="sxs-lookup"><span data-stu-id="d3e4d-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="d3e4d-106">オブジェクト変数の名前を通常使用する箇所で `Me` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3e4d-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="d3e4d-107">`Me` はオブジェクト変数と同様に動作しますが、宣言したり、何かを代入したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3e4d-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="d3e4d-108">`Me` では常に現在のインスタンスが参照されます。</span><span class="sxs-lookup"><span data-stu-id="d3e4d-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e4d-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3e4d-109">See also</span></span>

- [<span data-ttu-id="d3e4d-110">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="d3e4d-110">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="d3e4d-111">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="d3e4d-111">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="d3e4d-112">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="d3e4d-112">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
