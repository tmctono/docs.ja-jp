---
title: M_ResponseHeaders CoreResponseData フィールド
description: .NET の m_ResponseHeaders CoreResponseData フィールドについて説明します。 このフィールドは、サーバー応答に関連付けられたヘッダーを持つ WebHeaderCollection 型です。
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 7c7b896193cb81e9fc9e3ec28110359003a36728
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989784"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="a2557-104">CoreResponseData \_ ResponseHeaders フィールド</span><span class="sxs-lookup"><span data-stu-id="a2557-104">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="a2557-105">`CoreResponseData.m_ResponseHeaders`は、 <xref:System.Net.WebHeaderCollection> サーバーの応答に関連付けられているヘッダーのです。</span><span class="sxs-lookup"><span data-stu-id="a2557-105">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2557-106">構文</span><span class="sxs-lookup"><span data-stu-id="a2557-106">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="a2557-107">この API は、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="a2557-107">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="a2557-108">代わりに、を使用して <xref:System.Diagnostics.DiagnosticSource> ネットワークコードをフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2557-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="a2557-109">「 [DiagnosticSource User'S Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2557-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="a2557-110">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a2557-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a2557-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2557-111">Requirements</span></span>

<span data-ttu-id="a2557-112">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a2557-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a2557-113">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="a2557-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a2557-114">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2557-114">**.NET Framework versions:** Available since 2.0.</span></span>
