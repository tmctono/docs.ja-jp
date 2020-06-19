---
title: M_StatusCode CoreResponseData フィールド
description: .NET の m_StatusCode CoreResponseData フィールドについて確認します。 フィールドは、HTTP 応答の状態を含む HttpStatusCode 型です。
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
ms.openlocfilehash: 05950290bde96511432941ce679e663126878663
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989777"
---
# <a name="coreresponsedatam_statuscode-field"></a><span data-ttu-id="f3381-104">CoreResponseData \_ StatusCode フィールド</span><span class="sxs-lookup"><span data-stu-id="f3381-104">CoreResponseData.m\_StatusCode Field</span></span>

<span data-ttu-id="f3381-105">`CoreResponseData.m_StatusCode`<xref:System.Net.HttpStatusCode>応答の状態を表すです。</span><span class="sxs-lookup"><span data-stu-id="f3381-105">`CoreResponseData.m_StatusCode` is an <xref:System.Net.HttpStatusCode> containing the status of the response.</span></span>

## <a name="syntax"></a><span data-ttu-id="f3381-106">構文</span><span class="sxs-lookup"><span data-stu-id="f3381-106">Syntax</span></span>
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> <span data-ttu-id="f3381-107">この API は、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="f3381-107">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="f3381-108">代わりに、を使用して <xref:System.Diagnostics.DiagnosticSource> ネットワークコードをフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3381-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="f3381-109">「 [DiagnosticSource User'S Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3381-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="f3381-110">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f3381-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f3381-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f3381-111">Requirements</span></span>

<span data-ttu-id="f3381-112">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f3381-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f3381-113">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="f3381-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f3381-114">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3381-114">**.NET Framework versions:** Available since 2.0.</span></span>
