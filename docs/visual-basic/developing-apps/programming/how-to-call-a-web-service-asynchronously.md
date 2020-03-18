---
title: '方法 : Web サービスを非同期で呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: d288cc1f2991a8f504dc9f1b206bba76fa378b75
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "76794561"
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a><span data-ttu-id="87f55-102">方法: Web サービスを非同期で呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87f55-102">How to: Call a Web Service Asynchronously (Visual Basic)</span></span>

<span data-ttu-id="87f55-103">この例では、Web サービスの非同期ハンドラー イベントにハンドラーをアタッチして、非同期メソッド呼び出しの結果を取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="87f55-103">This example attaches a handler to a Web service's asynchronous handler event, so that it can retrieve the result of an asynchronous method call.</span></span> <span data-ttu-id="87f55-104">この例では、`http://www.xmethods.net` にある DemoTemperatureService Web サービスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="87f55-104">This example used the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span>

<span data-ttu-id="87f55-105">Visual Studio 統合開発環境 (IDE) でプロジェクトの Web サービスを参照すると、この Web サービスが `My.WebServices` オブジェクトに追加され、指定された Web サービスにアクセスするためのクライアント プロキシ クラスが IDE によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="87f55-105">When you reference a Web service in your project in the Visual Studio Integrated Development Environment (IDE), it is added to the `My.WebServices` object, and the IDE generates a client proxy class to access a specified Web service</span></span>

<span data-ttu-id="87f55-106">プロキシ クラスを使用すると、Web サービス メソッドを同期的に呼び出すことができ、この場合、アプリケーションは関数が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="87f55-106">The proxy class allows you to call the Web service methods synchronously, where your application waits for the function to complete.</span></span> <span data-ttu-id="87f55-107">また、プロキシはメソッドを非同期的に呼び出すために使用できる追加のメンバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="87f55-107">In addition, the proxy creates additional members to help call the method asynchronously.</span></span> <span data-ttu-id="87f55-108">Web サービス関数 *NameOfWebServiceFunction* ごとに、プロキシは *NameOfWebServiceFunction*`Async` サブルーチン、*NameOfWebServiceFunction*`Completed` イベント、および *NameOfWebServiceFunction*`CompletedEventArgs` クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="87f55-108">For each Web service function, *NameOfWebServiceFunction*, the proxy creates a *NameOfWebServiceFunction*`Async` subroutine, a *NameOfWebServiceFunction*`Completed` event, and a *NameOfWebServiceFunction*`CompletedEventArgs` class.</span></span> <span data-ttu-id="87f55-109">この例では、DemoTemperatureService Web サービスの `getTemp` 関数にアクセスする非同期メンバーの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="87f55-109">This example demonstrates how to use the asynchronous members to access the `getTemp` function of the DemoTemperatureService Web service.</span></span>

> [!NOTE]
> <span data-ttu-id="87f55-110">ASP.NET では `My.WebServices` オブジェクトがサポートされていないため、このコードは Web アプリケーションでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="87f55-110">This code does not work in Web applications, because ASP.NET does not support the `My.WebServices` object.</span></span>

## <a name="call-a-web-service-asynchronously"></a><span data-ttu-id="87f55-111">Web サービスを非同期で呼び出す</span><span class="sxs-lookup"><span data-stu-id="87f55-111">Call a Web service asynchronously</span></span>

1. <span data-ttu-id="87f55-112">`http://www.xmethods.net` にある DemoTemperatureService Web サービスを参照します。</span><span class="sxs-lookup"><span data-stu-id="87f55-112">Reference the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span> <span data-ttu-id="87f55-113">アドレスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87f55-113">The address is</span></span>

    ```http
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl
    ```

2. <span data-ttu-id="87f55-114">`getTempCompleted` イベントのイベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="87f55-114">Add an event handler for the `getTempCompleted` event:</span></span>

    ```vb
    Private Sub getTempCompletedHandler(ByVal sender As Object,
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)

        MsgBox("Temperature: " & e.Result)
    End Sub
    ```

    > [!NOTE]
    > <span data-ttu-id="87f55-115">`Handles` ステートメントを使用して、イベント ハンドラーを `My.WebServices` オブジェクトのイベントに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="87f55-115">You cannot use the `Handles` statement to associate an event handler with the `My.WebServices` object's events.</span></span>

3. <span data-ttu-id="87f55-116">イベント ハンドラーが `getTempCompleted` イベントに追加されたかどうかを追跡するためのフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="87f55-116">Add a field to track if the event handler has been added to the `getTempCompleted` event:</span></span>

    ```vb
    Private handlerAttached As Boolean = False
    ```

4. <span data-ttu-id="87f55-117">必要に応じて、イベント ハンドラーを `getTempCompleted` イベントに追加するメソッドを追加し、`getTempAsync` メソッドを呼び出すメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="87f55-117">Add a method to add the event handler to the `getTempCompleted` event, if necessary, and to call the `getTempAsync` method:</span></span>

    ```vb
    Sub CallGetTempAsync(ByVal zipCode As Integer)
        If Not handlerAttached Then
            AddHandler My.WebServices.
                TemperatureService.getTempCompleted,
                AddressOf Me.TS_getTempCompleted
            handlerAttached = True
        End If
        My.WebServices.TemperatureService.getTempAsync(zipCode)
    End Sub
    ```

    <span data-ttu-id="87f55-118">`getTemp` Web メソッドを非同期的に呼び出すには、`CallGetTempAsync` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="87f55-118">To call the `getTemp` Web method asynchronously, call the `CallGetTempAsync` method.</span></span> <span data-ttu-id="87f55-119">Web メソッドが終了すると、その戻り値が `getTempCompletedHandler` イベント ハンドラーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="87f55-119">When the Web method finishes, its return value is passed to the `getTempCompletedHandler` event handler.</span></span>

## <a name="see-also"></a><span data-ttu-id="87f55-120">参照</span><span class="sxs-lookup"><span data-stu-id="87f55-120">See also</span></span>

- [<span data-ttu-id="87f55-121">アプリケーションの Web サービスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="87f55-121">Accessing Application Web Services</span></span>](accessing-application-web-services.md)
- [<span data-ttu-id="87f55-122">My.WebServices オブジェクト</span><span class="sxs-lookup"><span data-stu-id="87f55-122">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
