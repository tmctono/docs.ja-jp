---
title: ServicePointManager. s_ServicePointTable フィールド
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
ms.openlocfilehash: 272a0c113fd70d804c763ba0e7e6e9a4a4ee04ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214920"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="39aeb-102">ServicePointManager. s\_Servicepointmanager フィールド</span><span class="sxs-lookup"><span data-stu-id="39aeb-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="39aeb-103">`ServicePointManager.s_ServicePointTable` は、<xref:System.AppDomain>内のアクティブな HTTP 接続 (<xref:System.Net.ServicePoint>s) の一覧を含む <xref:System.Collections.Hashtable> です。</span><span class="sxs-lookup"><span data-stu-id="39aeb-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="39aeb-104">構文</span><span class="sxs-lookup"><span data-stu-id="39aeb-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="39aeb-105">`ServicePointManager.s_ServicePointTable` フィールドはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="39aeb-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="39aeb-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="39aeb-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="39aeb-107">要件</span><span class="sxs-lookup"><span data-stu-id="39aeb-107">Requirements</span></span>

<span data-ttu-id="39aeb-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="39aeb-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="39aeb-109">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="39aeb-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="39aeb-110">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="39aeb-110">**.NET Framework versions:** Available since 2.0.</span></span>
