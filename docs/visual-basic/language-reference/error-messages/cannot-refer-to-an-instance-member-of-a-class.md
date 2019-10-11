---
title: クラスの明示的なインスタンスを指定しないで、共有メソッドまたは共有メンバー初期化子内からクラスのインスタンス メンバーへ参照することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: 9b388685299469d5865d57b698e3a66de912fa84
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250201"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="02d3e-102">クラスの明示的なインスタンスを指定しないで、共有メソッドまたは共有メンバー初期化子内からクラスのインスタンス メンバーへ参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="02d3e-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>

<span data-ttu-id="02d3e-103">共有プロシージャ内から、クラスの共有されていないメンバーを参照しようとしました。</span><span class="sxs-lookup"><span data-stu-id="02d3e-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="02d3e-104">このような状況を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="02d3e-104">The following example demonstrates such a situation:</span></span>
  
```vb  
Class Sample
    Public x as Integer  
    Public Shared Sub SetX()
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="02d3e-105">前の例では、代入ステートメント `x = 10` によって、このエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="02d3e-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="02d3e-106">これは、共有プロシージャがインスタンス変数にアクセスしようとしているためです。</span><span class="sxs-lookup"><span data-stu-id="02d3e-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="02d3e-107">変数 `x` は[Shared](../modifiers/shared.md)として宣言されていないため、インスタンスメンバーです。</span><span class="sxs-lookup"><span data-stu-id="02d3e-107">The variable `x` is an instance member because it is not declared as [Shared](../modifiers/shared.md).</span></span> <span data-ttu-id="02d3e-108">クラス `Sample` の各インスタンスには、独自の個別の変数 `x` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="02d3e-108">Each instance of class `Sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="02d3e-109">1つのインスタンスが `x` の値を設定または変更した場合、他のインスタンスの `x` の値には影響しません。</span><span class="sxs-lookup"><span data-stu-id="02d3e-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>
  
 <span data-ttu-id="02d3e-110">ただし、`SetX` というプロシージャは、クラス `Sample` のすべてのインスタンスの間で `Shared` です。</span><span class="sxs-lookup"><span data-stu-id="02d3e-110">However, the procedure `SetX` is `Shared` among all instances of class `Sample`.</span></span> <span data-ttu-id="02d3e-111">これは、クラスの1つのインスタンスに関連付けられておらず、個別のインスタンスとは独立して動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="02d3e-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="02d3e-112">特定のインスタンスとの接続がないため、`setX` はインスタンス変数にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="02d3e-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="02d3e-113">@No__t 0 の変数でのみ動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02d3e-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="02d3e-114">@No__t-0 の場合、共有変数の値を設定または変更すると、その新しい値はクラスのすべてのインスタンスで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="02d3e-114">When `SetX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>
  
 <span data-ttu-id="02d3e-115">**エラー ID:** BC30369</span><span class="sxs-lookup"><span data-stu-id="02d3e-115">**Error ID:** BC30369</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="02d3e-116">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="02d3e-116">To correct this error</span></span>
  
1. <span data-ttu-id="02d3e-117">メンバーをクラスのすべてのインスタンス間で共有するか、インスタンスごとに個別に保持するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="02d3e-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>

2. <span data-ttu-id="02d3e-118">メンバーの1つのコピーをすべてのインスタンス間で共有する場合は、メンバー宣言に `Shared` キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="02d3e-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="02d3e-119">プロシージャ宣言で @no__t 0 キーワードを保持します。</span><span class="sxs-lookup"><span data-stu-id="02d3e-119">Retain the `Shared` keyword in the procedure declaration.</span></span>

3. <span data-ttu-id="02d3e-120">各インスタンスがメンバーの個別のコピーを持つようにする場合は、メンバー宣言に `Shared` を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="02d3e-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="02d3e-121">プロシージャ宣言から @no__t 0 キーワードを削除します。</span><span class="sxs-lookup"><span data-stu-id="02d3e-121">Remove the `Shared` keyword from the procedure declaration.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="02d3e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="02d3e-122">See also</span></span>

- [<span data-ttu-id="02d3e-123">Shared</span><span class="sxs-lookup"><span data-stu-id="02d3e-123">Shared</span></span>](../modifiers/shared.md)
