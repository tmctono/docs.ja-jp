---
title: m_StatusCode フィールド
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
ms.openlocfilehash: dfed9a748e959f0f751408566c7cbb4d2fa13e3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156074"
---
# <a name="coreresponsedatam_statuscode-field"></a><span data-ttu-id="2d012-102">\_ステータスコード フィールド</span><span class="sxs-lookup"><span data-stu-id="2d012-102">CoreResponseData.m\_StatusCode Field</span></span>

<span data-ttu-id="2d012-103">`CoreResponseData.m_StatusCode`は応答<xref:System.Net.HttpStatusCode>のステータスを含むです。</span><span class="sxs-lookup"><span data-stu-id="2d012-103">`CoreResponseData.m_StatusCode` is an <xref:System.Net.HttpStatusCode> containing the status of the response.</span></span>

## <a name="syntax"></a><span data-ttu-id="2d012-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d012-104">Syntax</span></span>
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> <span data-ttu-id="2d012-105">この API は、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="2d012-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="2d012-106">代わりに、 を<xref:System.Diagnostics.DiagnosticSource>使用してネットワーク コードをフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d012-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="2d012-107">[診断ソースユーザーズガイドを](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d012-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="2d012-108">マイクロソフトでは、どのような状況でも、運用環境のアプリケーションでこのクラスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d012-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2d012-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2d012-109">Requirements</span></span>

<span data-ttu-id="2d012-110">**名前空間:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2d012-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2d012-111">**アセンブリ:** システム (システム.dll 内)</span><span class="sxs-lookup"><span data-stu-id="2d012-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="2d012-112">**.NET フレームワークのバージョン:** 2.0 以降で利用可能。</span><span class="sxs-lookup"><span data-stu-id="2d012-112">**.NET Framework versions:** Available since 2.0.</span></span>
