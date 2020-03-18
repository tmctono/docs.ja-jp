---
title: アプリケーションの Web サービスへのアクセス
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: ad616bd46f92261ec5ad6ae81d0db48138631ed1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349225"
---
# <a name="accessing-application-web-services-visual-basic"></a><span data-ttu-id="91083-102">アプリケーションの Web サービスへのアクセス (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91083-102">Accessing Application Web Services (Visual Basic)</span></span>

<span data-ttu-id="91083-103">`My.WebServices` オブジェクトは、現在のプロジェクトにより参照されている各 Web サービスのインスタンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="91083-103">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="91083-104">各インスタンスは要求に応じてインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="91083-104">Each instance is instantiated on demand.</span></span> <span data-ttu-id="91083-105">これらの Web サービスには `My.WebServices` オブジェクトのプロパティを介してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="91083-105">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="91083-106">プロパティの名前は、プロパティがアクセスする Web サービスの名前と同じになります。</span><span class="sxs-lookup"><span data-stu-id="91083-106">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="91083-107"><xref:System.Web.Services.Protocols.SoapHttpClientProtocol> から継承されたクラスはすべて Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="91083-107">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span>

## <a name="tasks"></a><span data-ttu-id="91083-108">処理手順</span><span class="sxs-lookup"><span data-stu-id="91083-108">Tasks</span></span>

<span data-ttu-id="91083-109">次の表は、アプリケーションにより参照される Web サービスにアクセスする方法を一覧にしたものです。</span><span class="sxs-lookup"><span data-stu-id="91083-109">The following table lists possible ways to access Web services referenced by an application.</span></span>

|<span data-ttu-id="91083-110">ターゲット</span><span class="sxs-lookup"><span data-stu-id="91083-110">To</span></span>|<span data-ttu-id="91083-111">参照先</span><span class="sxs-lookup"><span data-stu-id="91083-111">See</span></span>|
|---|---|
|<span data-ttu-id="91083-112">Web サービスを呼び出す</span><span class="sxs-lookup"><span data-stu-id="91083-112">Call a Web service</span></span>|[<span data-ttu-id="91083-113">My.WebServices オブジェクト</span><span class="sxs-lookup"><span data-stu-id="91083-113">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)|
|<span data-ttu-id="91083-114">Web サービスを非同期で呼び出し、完了時にイベントを処理する</span><span class="sxs-lookup"><span data-stu-id="91083-114">Call a Web service asynchronously and handle an event when it completes</span></span>|[<span data-ttu-id="91083-115">方法 : Web サービスを非同期で呼び出す</span><span class="sxs-lookup"><span data-stu-id="91083-115">How to: Call a Web Service Asynchronously</span></span>](../../../visual-basic/developing-apps/programming/how-to-call-a-web-service-asynchronously.md)|

## <a name="see-also"></a><span data-ttu-id="91083-116">参照</span><span class="sxs-lookup"><span data-stu-id="91083-116">See also</span></span>

- [<span data-ttu-id="91083-117">My.WebServices オブジェクト</span><span class="sxs-lookup"><span data-stu-id="91083-117">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
