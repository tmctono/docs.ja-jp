---
title: M_ResponseHeaders CoreResponseData フィールド
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
ms.openlocfilehash: df0b592a5f85d4c99dee4ecb60963f4abb560a13
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741009"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="531d8-102">CoreResponseData\_ResponseHeaders フィールド</span><span class="sxs-lookup"><span data-stu-id="531d8-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="531d8-103">`CoreResponseData.m_ResponseHeaders` は、サーバーの応答に関連付けられているヘッダーの <xref:System.Net.WebHeaderCollection> です。</span><span class="sxs-lookup"><span data-stu-id="531d8-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="531d8-104">構文</span><span class="sxs-lookup"><span data-stu-id="531d8-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="531d8-105">この API は、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="531d8-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="531d8-106">代わりに、<xref:System.Diagnostics.DiagnosticSource> を使用してネットワークコードをフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="531d8-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="531d8-107">「 [DiagnosticSource User'S Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="531d8-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="531d8-108">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="531d8-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="531d8-109">要件</span><span class="sxs-lookup"><span data-stu-id="531d8-109">Requirements</span></span>

<span data-ttu-id="531d8-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="531d8-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="531d8-111">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="531d8-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="531d8-112">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="531d8-112">**.NET Framework versions:** Available since 2.0.</span></span>
