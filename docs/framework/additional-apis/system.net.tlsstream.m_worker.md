---
title: TlsStream. m_Worker フィールド (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.TlsStream.m_Worker
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: d335820d13e1e15e054e824a284615cdbf6c2094
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847242"
---
# <a name="tlsstreamm_worker-field"></a><span data-ttu-id="165c9-102">TlsStream. m_Worker フィールド</span><span class="sxs-lookup"><span data-stu-id="165c9-102">TlsStream.m_Worker Field</span></span>

<span data-ttu-id="165c9-103">SSL ストリームの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="165c9-103">Represents the state of the SSL stream.</span></span>

## <a name="syntax"></a><span data-ttu-id="165c9-104">構文</span><span class="sxs-lookup"><span data-stu-id="165c9-104">Syntax</span></span>

```csharp
private SslState m_Worker;
```

## <a name="field-value"></a><span data-ttu-id="165c9-105">フィールド値</span><span class="sxs-lookup"><span data-stu-id="165c9-105">Field value</span></span>

`System.Net.Security.SslState`  
<span data-ttu-id="165c9-106">SSL ストリームの状態。</span><span class="sxs-lookup"><span data-stu-id="165c9-106">The state of the SSL stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="165c9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="165c9-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="165c9-108">`TlsStream.m_Worker` フィールドはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="165c9-108">The `TlsStream.m_Worker` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="165c9-109">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="165c9-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="165c9-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="165c9-110">Requirements</span></span>

<span data-ttu-id="165c9-111">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="165c9-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="165c9-112">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="165c9-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="165c9-113">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="165c9-113">**.NET Framework versions:** Available since 2.0.</span></span>
