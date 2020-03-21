---
title: サービスポイント.m_ConnectionGroupListフィールド
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
ms.openlocfilehash: 2b1b46085ed035b67fd01447727b406fe3895980
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155896"
---
# <a name="servicepointm_connectiongrouplist-field"></a><span data-ttu-id="f65d1-102">\_接続グループ リスト フィールド</span><span class="sxs-lookup"><span data-stu-id="f65d1-102">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="f65d1-103">`ServicePoint.m_ConnectionGroupList`は接続<xref:System.Collections.Hashtable>グループの 1 で、それぞれが 's URI の接続を<xref:System.Net.ServicePoint>保持しています。</span><span class="sxs-lookup"><span data-stu-id="f65d1-103">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="f65d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="f65d1-104">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="f65d1-105">フィールド`ServicePoint.m_ConnectionGroupList`はプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="f65d1-105">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f65d1-106">マイクロソフトは、どのような状況においても、本稼動アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f65d1-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f65d1-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="f65d1-107">Requirements</span></span>

<span data-ttu-id="f65d1-108">**名前空間:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f65d1-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f65d1-109">**アセンブリ:** システム (システム.dll 内)</span><span class="sxs-lookup"><span data-stu-id="f65d1-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f65d1-110">**.NET フレームワークのバージョン:** 2.0 以降で利用可能。</span><span class="sxs-lookup"><span data-stu-id="f65d1-110">**.NET Framework versions:** Available since 2.0.</span></span>
