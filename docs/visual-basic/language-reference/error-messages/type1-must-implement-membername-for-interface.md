---
title: <type1>'<typename>' は、インターフェイス '<membername>' に対して '<interfacename>' を実装しなければなりません。
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a824b66eaad964049ced5cae5eb2cc370d00ba7f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696891"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="5bf1b-102">\<type1 > '\<typename > ' は、インターフェイス '\<interfacename > ' に '\<membername > ' を実装しなければなりません</span><span class="sxs-lookup"><span data-stu-id="5bf1b-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="5bf1b-103">'\<typename > ' は、インターフェイス '\<interfacename > ' に対して '\<membername > ' を実装しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5bf1b-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="5bf1b-104">実装するプロパティには、' ReadOnly '/' WriteOnly ' 指定子が一致しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5bf1b-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="5bf1b-105">インターフェイスを実装するクラスまたは構造体が要求しますが、インターフェイスで定義されたプロシージャ、プロパティ、またはイベントを実装しません。</span><span class="sxs-lookup"><span data-stu-id="5bf1b-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="5bf1b-106">インターフェイスのすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bf1b-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="5bf1b-107">**エラー ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="5bf1b-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5bf1b-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="5bf1b-108">To correct this error</span></span>  
  
1. <span data-ttu-id="5bf1b-109">インターフェイスで定義されているものと同じ名前およびシグネチャを持つメンバーを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5bf1b-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="5bf1b-110">少なくとも `End Function`、`End Sub`、または `End Property` ステートメントを含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5bf1b-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="5bf1b-111">`Function`、`Sub`、`Property`、または `Event` ステートメントの末尾に `Implements` 句を追加します。</span><span class="sxs-lookup"><span data-stu-id="5bf1b-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="5bf1b-112">例 :</span><span class="sxs-lookup"><span data-stu-id="5bf1b-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="5bf1b-113">プロパティを実装するときは、インターフェイス定義と同じ方法で `ReadOnly` または `WriteOnly` が使用されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5bf1b-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="5bf1b-114">プロパティを実装する場合は、必要に応じて `Get` および `Set` プロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5bf1b-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf1b-115">参照</span><span class="sxs-lookup"><span data-stu-id="5bf1b-115">See also</span></span>

- [<span data-ttu-id="5bf1b-116">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="5bf1b-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="5bf1b-117">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5bf1b-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
