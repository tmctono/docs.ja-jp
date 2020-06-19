---
title: _HttpResponse HttpWebRequest フィールド
description: .NET の _HttpResponse HttpWebRequest フィールドについて説明します。 このフィールドは、http 要求からの HTTP 応答の詳細を含む HttpWebResponse 型です。
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
ms.openlocfilehash: 70058e1183abf5b6bfd172497f65a3ceb2344060
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989958"
---
# <a name="httpwebrequest_httpresponse-field"></a><span data-ttu-id="0f516-104">HttpWebRequest。 \_Httpresponse.cache フィールド</span><span class="sxs-lookup"><span data-stu-id="0f516-104">HttpWebRequest.\_HttpResponse Field</span></span>

<span data-ttu-id="0f516-105">`HttpWebRequest._HttpResponse`<xref:System.Net.HttpWebResponse>http 要求からの http 応答の詳細を格納している。</span><span class="sxs-lookup"><span data-stu-id="0f516-105">`HttpWebRequest._HttpResponse` is an <xref:System.Net.HttpWebResponse> containing HTTP response details from an HTTP request.</span></span> <span data-ttu-id="0f516-106">`null`HTTP 応答が受信されるまでの間でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="0f516-106">It can be `null` until an HTTP response is received.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f516-107">構文</span><span class="sxs-lookup"><span data-stu-id="0f516-107">Syntax</span></span>
  
```csharp  
internal HttpWebResponse _HttpResponse
```

> [!WARNING]
> <span data-ttu-id="0f516-108">`HttpWebRequest._HttpResponse`フィールドは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="0f516-108">The `HttpWebRequest._HttpResponse` field is internal and not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0f516-109">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0f516-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f516-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="0f516-110">Requirements</span></span>

<span data-ttu-id="0f516-111">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="0f516-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="0f516-112">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="0f516-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="0f516-113">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f516-113">**.NET Framework versions:** Available since 2.0.</span></span>
