---
title: Default プロパティ アクセスは、インターフェイス '<defaultpropertyname>' の継承インターフェイス メンバー '<interfacename1>' とインターフェイス '<defaultpropertyname>' の '<interfacename2>' との間で不適切です。
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 5f058c8e7d480b9145452ae85f186a6ac2ed0d56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803731"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a><span data-ttu-id="32bc6-102">Default プロパティ アクセスは継承インターフェイス メンバーの間であいまいな\<defaultpropertyname >' のインターフェイス '\<interfacename1 >' と'\<defaultpropertyname >' のインターフェイス '\<interfacename2 >'</span><span class="sxs-lookup"><span data-stu-id="32bc6-102">Default property access is ambiguous between the inherited interface members '\<defaultpropertyname>' of interface '\<interfacename1>' and '\<defaultpropertyname>' of interface '\<interfacename2>'</span></span>
<span data-ttu-id="32bc6-103">インターフェイスは、同じ名前の既定プロパティを宣言するそれぞれの 2 つのインターフェイスから継承します。</span><span class="sxs-lookup"><span data-stu-id="32bc6-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="32bc6-104">コンパイラは、この既定のプロパティを修飾なしに、アクセスを解決できません。</span><span class="sxs-lookup"><span data-stu-id="32bc6-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="32bc6-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="32bc6-105">The following example illustrates this.</span></span>  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="32bc6-106">指定すると`testObj(1)`コンパイラは既定のプロパティに解決しようとしています。</span><span class="sxs-lookup"><span data-stu-id="32bc6-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="32bc6-107">ただし、2 つ可能な既定プロパティは、継承のインターフェイスにより、コンパイラは、このエラーを通知するためです。</span><span class="sxs-lookup"><span data-stu-id="32bc6-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>  
  
 <span data-ttu-id="32bc6-108">**エラー ID:** BC30686</span><span class="sxs-lookup"><span data-stu-id="32bc6-108">**Error ID:** BC30686</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="32bc6-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="32bc6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="32bc6-110">同じ名前のメンバーを継承しないようにします。</span><span class="sxs-lookup"><span data-stu-id="32bc6-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="32bc6-111">前の例では場合、`testObj`のメンバーのいずれかの必要はありません、たとえば、 `Iface2`、次のように宣言します。</span><span class="sxs-lookup"><span data-stu-id="32bc6-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     <span data-ttu-id="32bc6-112">- または -</span><span class="sxs-lookup"><span data-stu-id="32bc6-112">-or-</span></span>  
  
-   <span data-ttu-id="32bc6-113">クラスで継承するインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="32bc6-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="32bc6-114">これらの異なる名前を持つ継承されたプロパティを実装できます。</span><span class="sxs-lookup"><span data-stu-id="32bc6-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="32bc6-115">ただし、それらの 1 つだけでは、実装するクラスの既定のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="32bc6-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="32bc6-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="32bc6-116">The following example illustrates this.</span></span>  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="32bc6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="32bc6-117">See also</span></span>

- [<span data-ttu-id="32bc6-118">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32bc6-118">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
