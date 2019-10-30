---
title: HttpWebRequest. _HttpResponse フィールド
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._HttpResponse
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: eab9b789-beb4-4c28-b2d8-78debc7ba129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d993021ccb87ccafb5f6f2fc4c6c7c288288adae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120075"
---
# <a name="httpwebrequest_httpresponse-field"></a><span data-ttu-id="7d8c0-102">HttpWebRequest.\_Httpresponse.cache フィールド</span><span class="sxs-lookup"><span data-stu-id="7d8c0-102">HttpWebRequest.\_HttpResponse Field</span></span>

<span data-ttu-id="7d8c0-103">`HttpWebRequest._HttpResponse` は、http 要求からの HTTP 応答の詳細を含む <xref:System.Net.HttpWebResponse> です。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-103">`HttpWebRequest._HttpResponse` is an <xref:System.Net.HttpWebResponse> containing HTTP response details from an HTTP request.</span></span> <span data-ttu-id="7d8c0-104">HTTP 応答を受信するまで `null` できます。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-104">It can be `null` until an HTTP response is received.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d8c0-105">構文</span><span class="sxs-lookup"><span data-stu-id="7d8c0-105">Syntax</span></span>
  
```csharp  
internal HttpWebResponse _HttpResponse
```

> [!WARNING]
> <span data-ttu-id="7d8c0-106">`HttpWebRequest._HttpResponse` フィールドは内部であり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-106">The `HttpWebRequest._HttpResponse` field is internal and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="7d8c0-107">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d8c0-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="7d8c0-108">Requirements</span></span>

<span data-ttu-id="7d8c0-109">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7d8c0-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7d8c0-110">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="7d8c0-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7d8c0-111">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-111">**.NET Framework versions:** Available since 2.0.</span></span>
