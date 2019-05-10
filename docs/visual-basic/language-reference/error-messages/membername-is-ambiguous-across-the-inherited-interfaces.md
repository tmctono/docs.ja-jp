---
title: "'<membername>' は、継承インターフェイス '<interfacename1>' および '<interfacename2>' 間ではあいまいです。"
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 71f8cb96c9981bbfc55236ea815fa5f5cb0e8aaf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622670"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="1cfba-102">'\<membername>' は、継承インターフェイス '\<interfacename1>' および '\<interfacename2>' 間ではあいまいです。</span><span class="sxs-lookup"><span data-stu-id="1cfba-102">'\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>
<span data-ttu-id="1cfba-103">インターフェイスは、複数のインターフェイスから同じ名前の 2 つ以上のメンバーを継承します。</span><span class="sxs-lookup"><span data-stu-id="1cfba-103">The interface inherits two or more members with the same name from multiple interfaces.</span></span>  
  
 <span data-ttu-id="1cfba-104">**エラー ID:** BC30685</span><span class="sxs-lookup"><span data-stu-id="1cfba-104">**Error ID:** BC30685</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1cfba-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1cfba-105">To correct this error</span></span>  
  
- <span data-ttu-id="1cfba-106">値のキャストを使用する基本インターフェイス例えば：</span><span class="sxs-lookup"><span data-stu-id="1cfba-106">Cast the value to the base interface that you want to use; for example:</span></span>  
  
    ```  
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
  
## <a name="see-also"></a><span data-ttu-id="1cfba-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cfba-107">See also</span></span>

- [<span data-ttu-id="1cfba-108">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1cfba-108">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
