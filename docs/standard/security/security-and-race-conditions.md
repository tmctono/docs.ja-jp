---
title: セキュリティと競合状態
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
ms.openlocfilehash: 09d8d0d6e85af04fe0fb00f53df408126012081e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186780"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="40a7b-102">セキュリティと競合状態</span><span class="sxs-lookup"><span data-stu-id="40a7b-102">Security and Race Conditions</span></span>
<span data-ttu-id="40a7b-103">もう一つの懸念事項は、レース条件によって悪用されるセキュリティホールの可能性です。</span><span class="sxs-lookup"><span data-stu-id="40a7b-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="40a7b-104">これが起こるいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="40a7b-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="40a7b-105">次のサブトピックでは、開発者が避けなければならないいくつかの主な落とし穴の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="40a7b-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="40a7b-106">Dispose メソッドの競合条件</span><span class="sxs-lookup"><span data-stu-id="40a7b-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="40a7b-107">クラスの**Dispose**メソッド (詳細については、「[ガベージ コレクション](../../../docs/standard/garbage-collection/index.md)」を参照) が同期されていない場合、次の例に示すように **、Dispose**内のクリーンアップ コードを複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="40a7b-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()
{  
    if (myObj != null)
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 <span data-ttu-id="40a7b-108">この**Dispose**実装は同期されていないため、最初の`Cleanup`1 つのスレッドから呼び出し、次に 2`_myObj`つ目のスレッドを呼び出す場合は**null**に設定できます。</span><span class="sxs-lookup"><span data-stu-id="40a7b-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="40a7b-109">これがセキュリティ上の問題であるかどうかは、コードの`Cleanup`実行時に何が起こるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="40a7b-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="40a7b-110">非同期**の Dispose**実装に関する大きな問題は、ファイルなどのリソース ハンドルの使用です。</span><span class="sxs-lookup"><span data-stu-id="40a7b-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="40a7b-111">不適切な破棄により、不適切なハンドルが使用され、セキュリティの脆弱性が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="40a7b-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="40a7b-112">コンストラクタの競合状況</span><span class="sxs-lookup"><span data-stu-id="40a7b-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="40a7b-113">アプリケーションによっては、クラス コンストラクターが完全に実行される前に、他のスレッドがクラス メンバーにアクセスできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="40a7b-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="40a7b-114">すべてのクラス コンストラクターを確認して、セキュリティ上の問題が発生しないかどうかを確認するか、必要に応じてスレッドを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40a7b-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="40a7b-115">キャッシュされたオブジェクトを含む競合条件</span><span class="sxs-lookup"><span data-stu-id="40a7b-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="40a7b-116">セキュリティ情報をキャッシュするコード、またはコード アクセス セキュリティ[Assert](../../../docs/framework/misc/using-the-assert-method.md)操作を使用するコードは、次の例に示すように、クラスの他の部分が適切に同期されていない場合にも競合状態に対して脆弱になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40a7b-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()
{  
    if (SomeDemandPasses())
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false;  
    }  
}  
void DoOtherWork()
{  
    if (fCallersOK)
    {  
        DoSomethingTrusted();  
    }  
    else
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 <span data-ttu-id="40a7b-117">同じオブジェクトを`DoOtherWork`持つ別のスレッドから他のパスを呼び出すことができる場合、信頼されていない呼び出し元は要求を超えてスリップできます。</span><span class="sxs-lookup"><span data-stu-id="40a7b-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="40a7b-118">コードでセキュリティ情報がキャッシュされる場合は、この脆弱性について確認してください。</span><span class="sxs-lookup"><span data-stu-id="40a7b-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="40a7b-119">ファイナライザーのレース条件</span><span class="sxs-lookup"><span data-stu-id="40a7b-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="40a7b-120">競合状態は、静的リソースまたはアンマネージ リソースを参照するオブジェクトで発生し、ファイナライザーで解放されることもあります。</span><span class="sxs-lookup"><span data-stu-id="40a7b-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="40a7b-121">クラスのファイナライザーで操作されるリソースを複数のオブジェクトが共有する場合、そのオブジェクトは、そのリソースへのすべてのアクセスを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40a7b-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a7b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="40a7b-122">See also</span></span>

- [<span data-ttu-id="40a7b-123">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="40a7b-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
