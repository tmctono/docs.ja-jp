---
title: _HttpResponse HttpWebRequest フィールド
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
ms.openlocfilehash: 236298921ecd286ddba4e74dbce1b63e96055412
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215101"
---
# <a name="httpwebrequest_httpresponse-field"></a><span data-ttu-id="5cc78-102">HttpWebRequest.\_Httpresponse.cache フィールド</span><span class="sxs-lookup"><span data-stu-id="5cc78-102">HttpWebRequest.\_HttpResponse Field</span></span>

<span data-ttu-id="5cc78-103">`HttpWebRequest._HttpResponse` は、http 要求からの HTTP 応答の詳細を含む <xref:System.Net.HttpWebResponse> です。</span><span class="sxs-lookup"><span data-stu-id="5cc78-103">`HttpWebRequest._HttpResponse` is an <xref:System.Net.HttpWebResponse> containing HTTP response details from an HTTP request.</span></span> <span data-ttu-id="5cc78-104">HTTP 応答を受信するまで `null` できます。</span><span class="sxs-lookup"><span data-stu-id="5cc78-104">It can be `null` until an HTTP response is received.</span></span>

## <a name="syntax"></a><span data-ttu-id="5cc78-105">構文</span><span class="sxs-lookup"><span data-stu-id="5cc78-105">Syntax</span></span>
  
```csharp  
internal HttpWebResponse _HttpResponse
```

> [!WARNING]
> <span data-ttu-id="5cc78-106">`HttpWebRequest._HttpResponse` フィールドは内部であり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="5cc78-106">The `HttpWebRequest._HttpResponse` field is internal and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="5cc78-107">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5cc78-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5cc78-108">要件</span><span class="sxs-lookup"><span data-stu-id="5cc78-108">Requirements</span></span>

<span data-ttu-id="5cc78-109">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="5cc78-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="5cc78-110">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="5cc78-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="5cc78-111">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5cc78-111">**.NET Framework versions:** Available since 2.0.</span></span>
