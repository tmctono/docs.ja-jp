---
title: ServicePoint.m_ConnectionGroupList フィールド
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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 85359492fbf06942a57c51142620cab015999b31
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300863"
---
# <a name="servicepointmconnectiongrouplist-field"></a><span data-ttu-id="ba228-102">ServicePoint.m\_ConnectionGroupList フィールド</span><span class="sxs-lookup"><span data-stu-id="ba228-102">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="ba228-103">`ServicePoint.m_ConnectionGroupList` <xref:System.Collections.Hashtable>の接続を保持する各接続のグループの<xref:System.Net.ServicePoint>の URI。</span><span class="sxs-lookup"><span data-stu-id="ba228-103">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba228-104">構文</span><span class="sxs-lookup"><span data-stu-id="ba228-104">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="ba228-105">`ServicePoint.m_ConnectionGroupList`フィールドはプライベートであり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="ba228-105">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="ba228-106">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ba228-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba228-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="ba228-107">Requirements</span></span>

<span data-ttu-id="ba228-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="ba228-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="ba228-109">**アセンブリ:** (System.dll) のシステム</span><span class="sxs-lookup"><span data-stu-id="ba228-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="ba228-110">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="ba228-110">**.NET Framework versions:** Available since 2.0.</span></span>
