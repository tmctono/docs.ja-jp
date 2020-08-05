---
title: セキュリティと競合状態
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
ms.date: 07/15/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
ms.openlocfilehash: a667bf69ba72cbe203bd2603c4c6b7a1e58a6d43
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555111"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="32194-102">セキュリティと競合状態</span><span class="sxs-lookup"><span data-stu-id="32194-102">Security and Race Conditions</span></span>

<span data-ttu-id="32194-103">問題のもう1つの領域は、競合状態によってセキュリティホールが悪用される可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="32194-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="32194-104">これにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="32194-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="32194-105">次のサブトピックでは、開発者が回避する必要のある主要な落とし穴をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="32194-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="32194-106">Dispose メソッドの競合状態</span><span class="sxs-lookup"><span data-stu-id="32194-106">Race Conditions in the Dispose Method</span></span>  

<span data-ttu-id="32194-107">クラスの**dispose**メソッド (詳細については、「[ガベージコレクション](../garbage-collection/index.md)」を参照) が同期されていない場合は、次の例に示すように、 **dispose**内のクリーンアップコードを複数回実行できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32194-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
<span data-ttu-id="32194-108">この**Dispose**実装は同期されていないため、 `Cleanup` `_myObj` が**null**に設定される前に、最初の1つのスレッドと2番目のスレッドからを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="32194-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="32194-109">これがセキュリティ上の問題であるかどうかは、コードが実行されたときの動作によって異なり `Cleanup` ます。</span><span class="sxs-lookup"><span data-stu-id="32194-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="32194-110">非同期の**Dispose**実装の主な問題は、ファイルなどのリソースハンドルを使用することです。</span><span class="sxs-lookup"><span data-stu-id="32194-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="32194-111">不適切な破棄によって、誤ったハンドルが使用されることがあります。これは、多くの場合、セキュリティの脆弱性につながります。</span><span class="sxs-lookup"><span data-stu-id="32194-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="32194-112">コンストラクターの競合状態</span><span class="sxs-lookup"><span data-stu-id="32194-112">Race Conditions in Constructors</span></span>

<span data-ttu-id="32194-113">アプリケーションによっては、クラスコンストラクターが完全に実行される前に、他のスレッドがクラスメンバーにアクセスできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="32194-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="32194-114">すべてのクラスコンストラクターを確認して、このような場合にセキュリティの問題が発生していないことを確認し、必要に応じてスレッドを同期してください。</span><span class="sxs-lookup"><span data-stu-id="32194-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="32194-115">キャッシュされたオブジェクトを使用した競合状態</span><span class="sxs-lookup"><span data-stu-id="32194-115">Race Conditions with Cached Objects</span></span>  

<span data-ttu-id="32194-116">次の例に示すように、セキュリティ情報をキャッシュしたり、コードアクセスセキュリティ[アサート](../../framework/misc/using-the-assert-method.md)操作を使用したりするコードは、クラスの他の部分が適切に同期されていない場合に、競合状態に対して脆弱になることがあります。</span><span class="sxs-lookup"><span data-stu-id="32194-116">Code that caches security information or uses the code access security [Assert](../../framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
<span data-ttu-id="32194-117">同じオブジェクトを持つ別のスレッドから呼び出すことができるへのパスが他にもある場合は、信頼されて `DoOtherWork` いない呼び出し元が要求を過去にスリップする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32194-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
<span data-ttu-id="32194-118">コードでセキュリティ情報がキャッシュされている場合は、この脆弱性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="32194-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="32194-119">ファイナライザーでの競合状態</span><span class="sxs-lookup"><span data-stu-id="32194-119">Race Conditions in Finalizers</span></span>  

<span data-ttu-id="32194-120">競合状態は、静的またはアンマネージリソースを参照するオブジェクトでも発生し、その後、そのファイナライザーで解放されます。</span><span class="sxs-lookup"><span data-stu-id="32194-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="32194-121">クラスのファイナライザーで操作されているリソースを複数のオブジェクトが共有している場合、そのオブジェクトは、そのリソースへのすべてのアクセスを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32194-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32194-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="32194-122">See also</span></span>

- [<span data-ttu-id="32194-123">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="32194-123">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
- [<span data-ttu-id="32194-124">ASP.NET Core のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="32194-124">ASP.NET Core Security</span></span>](/aspnet/core/security/)
