---
title: セキュリティと競合状態
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57ceaedc7c38ae70a0db5a7fd584a765a7474aff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933810"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="a2e58-102">セキュリティと競合状態</span><span class="sxs-lookup"><span data-stu-id="a2e58-102">Security and Race Conditions</span></span>
<span data-ttu-id="a2e58-103">問題の別の領域は、競合状態によって生じるセキュリティ ホールが発生する可能性です。</span><span class="sxs-lookup"><span data-stu-id="a2e58-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="a2e58-104">これが発生するいくつかの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="a2e58-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="a2e58-105">次のサブトピックをアウトラインの主要な落とし穴を開発者は避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e58-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="a2e58-106">Dispose メソッドで競合状態</span><span class="sxs-lookup"><span data-stu-id="a2e58-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="a2e58-107">クラスの場合、 **Dispose**メソッド (詳細については、次を参照してください[ガベージ コレクション](../../../docs/standard/garbage-collection/index.md)) が同期されていないことができます内でクリーンアップ コード**Dispose**実行できる複数の。1 回、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="a2e58-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="a2e58-108">ため、この**Dispose**実装が同期されていない、可能性があります`Cleanup`最初の 1 つのスレッドとし前に、の 2 番目のスレッドによって呼び出される`_myObj`に設定されている**null**します。</span><span class="sxs-lookup"><span data-stu-id="a2e58-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="a2e58-109">これはセキュリティ上の問題であるかどうかによって起こる異なるときに、`Cleanup`コードの実行。</span><span class="sxs-lookup"><span data-stu-id="a2e58-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="a2e58-110">同期されていない主な課題**Dispose**実装は、ファイルなどのリソース ハンドルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2e58-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="a2e58-111">不適切な廃棄には、多くの場合、セキュリティの脆弱性につながる不適切なハンドルを使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="a2e58-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="a2e58-112">コンス トラクターでの競合状態</span><span class="sxs-lookup"><span data-stu-id="a2e58-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="a2e58-113">一部のアプリケーションでは、他のスレッドがそのクラス コンス トラクターが完全に実行する前にクラス メンバーにアクセスすることができる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2e58-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="a2e58-114">すべてのクラス コンス トラクターがないセキュリティの問題、発生するかに応じてスレッドを同期させる場合になっていることを確認するを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a2e58-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="a2e58-115">キャッシュされたオブジェクトの競合状態</span><span class="sxs-lookup"><span data-stu-id="a2e58-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="a2e58-116">セキュリティ情報をキャッシュしたり、コード アクセス セキュリティを使用するコード[Assert](../../../docs/framework/misc/using-the-assert-method.md)操作もされる恐れがあります競合状態、クラスの他の部分が適切に同期されていない場合、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="a2e58-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="a2e58-117">他のパスがある場合`DoOtherWork`が同じオブジェクトと別のスレッドから呼び出すことできますが、信頼されていないの呼び出し元は、過去の需要を遅らせることができます。</span><span class="sxs-lookup"><span data-stu-id="a2e58-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="a2e58-118">コードは、セキュリティ情報をキャッシュする場合は、この脆弱性を確認することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a2e58-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="a2e58-119">ファイナライザーでの競合状態</span><span class="sxs-lookup"><span data-stu-id="a2e58-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="a2e58-120">競合状態は、そのファイナライザーで解放し、静的またはアンマネージ リソースを参照するオブジェクトでも発生することができます。</span><span class="sxs-lookup"><span data-stu-id="a2e58-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="a2e58-121">複数のオブジェクトは、クラスのファイナライザーで操作されるリソースを共有している場合、オブジェクトは、そのリソースに対するすべてのアクセスを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e58-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e58-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2e58-122">See also</span></span>

- [<span data-ttu-id="a2e58-123">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a2e58-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
