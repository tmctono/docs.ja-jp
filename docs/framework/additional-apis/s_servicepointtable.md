---
title: フィールドs_ServicePointTable
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155816"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="6882a-102">\_サービスポイントテーブルフィールド</span><span class="sxs-lookup"><span data-stu-id="6882a-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="6882a-103">`ServicePointManager.s_ServicePointTable`<xref:System.Collections.Hashtable>は、 内のアクティブな HTTP 接続<xref:System.Net.ServicePoint>の一覧を<xref:System.AppDomain>含む ものです。</span><span class="sxs-lookup"><span data-stu-id="6882a-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="6882a-104">構文</span><span class="sxs-lookup"><span data-stu-id="6882a-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="6882a-105">フィールド`ServicePointManager.s_ServicePointTable`はプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="6882a-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6882a-106">マイクロソフトは、どのような状況においても、本稼動アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6882a-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6882a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="6882a-107">Requirements</span></span>

<span data-ttu-id="6882a-108">**名前空間:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="6882a-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="6882a-109">**アセンブリ:** システム (システム.dll 内)</span><span class="sxs-lookup"><span data-stu-id="6882a-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="6882a-110">**.NET フレームワークのバージョン:** 2.0 以降で利用可能。</span><span class="sxs-lookup"><span data-stu-id="6882a-110">**.NET Framework versions:** Available since 2.0.</span></span>
