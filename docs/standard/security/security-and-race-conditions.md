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
# <a name="security-and-race-conditions"></a>セキュリティと競合状態

問題のもう1つの領域は、競合状態によってセキュリティホールが悪用される可能性があることです。 これにはいくつかの方法があります。 次のサブトピックでは、開発者が回避する必要のある主要な落とし穴をいくつか紹介します。  
  
## <a name="race-conditions-in-the-dispose-method"></a>Dispose メソッドの競合状態  

クラスの**dispose**メソッド (詳細については、「[ガベージコレクション](../garbage-collection/index.md)」を参照) が同期されていない場合は、次の例に示すように、 **dispose**内のクリーンアップコードを複数回実行できる可能性があります。  
  
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
  
この**Dispose**実装は同期されていないため、 `Cleanup` `_myObj` が**null**に設定される前に、最初の1つのスレッドと2番目のスレッドからを呼び出すことができます。 これがセキュリティ上の問題であるかどうかは、コードが実行されたときの動作によって異なり `Cleanup` ます。 非同期の**Dispose**実装の主な問題は、ファイルなどのリソースハンドルを使用することです。 不適切な破棄によって、誤ったハンドルが使用されることがあります。これは、多くの場合、セキュリティの脆弱性につながります。  
  
## <a name="race-conditions-in-constructors"></a>コンストラクターの競合状態

アプリケーションによっては、クラスコンストラクターが完全に実行される前に、他のスレッドがクラスメンバーにアクセスできる場合があります。 すべてのクラスコンストラクターを確認して、このような場合にセキュリティの問題が発生していないことを確認し、必要に応じてスレッドを同期してください。  
  
## <a name="race-conditions-with-cached-objects"></a>キャッシュされたオブジェクトを使用した競合状態  

次の例に示すように、セキュリティ情報をキャッシュしたり、コードアクセスセキュリティ[アサート](../../framework/misc/using-the-assert-method.md)操作を使用したりするコードは、クラスの他の部分が適切に同期されていない場合に、競合状態に対して脆弱になることがあります。  
  
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
  
同じオブジェクトを持つ別のスレッドから呼び出すことができるへのパスが他にもある場合は、信頼されて `DoOtherWork` いない呼び出し元が要求を過去にスリップする可能性があります。  
  
コードでセキュリティ情報がキャッシュされている場合は、この脆弱性を確認してください。  
  
## <a name="race-conditions-in-finalizers"></a>ファイナライザーでの競合状態  

競合状態は、静的またはアンマネージリソースを参照するオブジェクトでも発生し、その後、そのファイナライザーで解放されます。 クラスのファイナライザーで操作されているリソースを複数のオブジェクトが共有している場合、そのオブジェクトは、そのリソースへのすべてのアクセスを同期する必要があります。  
  
## <a name="see-also"></a>関連項目

- [安全なコーディングのガイドライン](secure-coding-guidelines.md)
- [ASP.NET Core のセキュリティ](/aspnet/core/security/)
