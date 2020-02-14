---
title: ServicePoint. m_ConnectionGroupList フィールド
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePoint.m_ConnectionGroupList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: df8afb59-f0f6-4ddc-b3c1-839b9fc601d8
ms.openlocfilehash: f2759f82f335415edf7bab33edbd446eec6ffbb5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215518"
---
# <a name="servicepointm_connectiongrouplist-field"></a><span data-ttu-id="3af7d-102">ServicePoint. m\_ConnectionGroupList フィールド</span><span class="sxs-lookup"><span data-stu-id="3af7d-102">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="3af7d-103">`ServicePoint.m_ConnectionGroupList` は、それぞれ <xref:System.Net.ServicePoint>の URI の接続を保持する接続グループの <xref:System.Collections.Hashtable> です。</span><span class="sxs-lookup"><span data-stu-id="3af7d-103">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="3af7d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3af7d-104">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="3af7d-105">`ServicePoint.m_ConnectionGroupList` フィールドはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="3af7d-105">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="3af7d-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3af7d-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3af7d-107">要件</span><span class="sxs-lookup"><span data-stu-id="3af7d-107">Requirements</span></span>

<span data-ttu-id="3af7d-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="3af7d-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="3af7d-109">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="3af7d-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="3af7d-110">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3af7d-110">**.NET Framework versions:** Available since 2.0.</span></span>
