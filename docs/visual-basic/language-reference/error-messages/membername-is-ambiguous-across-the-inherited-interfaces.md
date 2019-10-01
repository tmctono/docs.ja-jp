---
title: "'<membername>' は、継承インターフェイス '<interfacename1>' および '<interfacename2>' 間ではあいまいです。"
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 06e0d8863c74041f81977b3187fe99a1d05bcd53
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700880"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="7d397-102">'\<membername>' は、継承インターフェイス '\<interfacename1>' および '\<interfacename2>' 間ではあいまいです。</span><span class="sxs-lookup"><span data-stu-id="7d397-102">'\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>
<span data-ttu-id="7d397-103">インターフェイスは、複数のインターフェイスから同じ名前を持つ2つ以上のメンバーを継承します。</span><span class="sxs-lookup"><span data-stu-id="7d397-103">The interface inherits two or more members with the same name from multiple interfaces.</span></span>  
  
 <span data-ttu-id="7d397-104">**エラー ID:** BC30685</span><span class="sxs-lookup"><span data-stu-id="7d397-104">**Error ID:** BC30685</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7d397-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="7d397-105">To correct this error</span></span>  
  
- <span data-ttu-id="7d397-106">使用する基本インターフェイスに値をキャストします。例えば：</span><span class="sxs-lookup"><span data-stu-id="7d397-106">Cast the value to the base interface that you want to use; for example:</span></span>  
  
    ```vb  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7d397-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d397-107">See also</span></span>

- [<span data-ttu-id="7d397-108">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d397-108">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
