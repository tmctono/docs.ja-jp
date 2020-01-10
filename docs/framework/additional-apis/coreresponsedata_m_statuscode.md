---
title: M_StatusCode CoreResponseData フィールド
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_StatusCode
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 8abe619a57cc61fc3502807f60deccbbd578f382
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740993"
---
# <a name="coreresponsedatam_statuscode-field"></a><span data-ttu-id="a5c8f-102">CoreResponseData\_StatusCode フィールド</span><span class="sxs-lookup"><span data-stu-id="a5c8f-102">CoreResponseData.m\_StatusCode Field</span></span>

<span data-ttu-id="a5c8f-103">`CoreResponseData.m_StatusCode` は、応答の状態を含む <xref:System.Net.HttpStatusCode> です。</span><span class="sxs-lookup"><span data-stu-id="a5c8f-103">`CoreResponseData.m_StatusCode` is an <xref:System.Net.HttpStatusCode> containing the status of the response.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5c8f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a5c8f-104">Syntax</span></span>
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> <span data-ttu-id="a5c8f-105">この API は、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="a5c8f-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="a5c8f-106">代わりに、<xref:System.Diagnostics.DiagnosticSource> を使用してネットワークコードをフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5c8f-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="a5c8f-107">「 [DiagnosticSource User'S Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5c8f-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="a5c8f-108">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a5c8f-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a5c8f-109">要件</span><span class="sxs-lookup"><span data-stu-id="a5c8f-109">Requirements</span></span>

<span data-ttu-id="a5c8f-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a5c8f-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a5c8f-111">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="a5c8f-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a5c8f-112">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5c8f-112">**.NET Framework versions:** Available since 2.0.</span></span>
