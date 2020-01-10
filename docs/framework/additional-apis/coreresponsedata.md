---
title: CoreResponseData クラス
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: fd0ffb982c22b0a8b6cb5dd677faafb9921bf5d9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741023"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="b1655-102">CoreResponseData クラス</span><span class="sxs-lookup"><span data-stu-id="b1655-102">CoreResponseData Class</span></span>

<span data-ttu-id="b1655-103">`CoreResponseData` クラスは、HTTP ヘッダーと応答本文の解析を表します。</span><span class="sxs-lookup"><span data-stu-id="b1655-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1655-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1655-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="b1655-105">この API は内部的なものであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="b1655-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="b1655-106">代わりに、<xref:System.Diagnostics.DiagnosticSource> を使用してネットワークコードをフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1655-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="b1655-107">「 [DiagnosticSource User'S Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1655-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="b1655-108">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b1655-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1655-109">要件</span><span class="sxs-lookup"><span data-stu-id="b1655-109">Requirements</span></span>

<span data-ttu-id="b1655-110">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b1655-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b1655-111">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="b1655-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="b1655-112">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1655-112">**.NET Framework versions:** Available since 2.0.</span></span>
