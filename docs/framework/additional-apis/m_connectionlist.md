---
title: ConnectionGroup. m_ConnectionList フィールド
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
ms.openlocfilehash: d53eeb54d212adb011dae138e103ea5b30f7fb99
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215531"
---
# <a name="connectiongroupm_connectionlist-field"></a><span data-ttu-id="1725e-102">ConnectionGroup. m\_Connectiongroup フィールド</span><span class="sxs-lookup"><span data-stu-id="1725e-102">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="1725e-103">`ConnectionGroup.m_ConnectionList` は、同じ URI を提供し、有効期限や認証などの他のいくつかのプロパティで同じ値を共有する接続オブジェクトの <xref:System.Collections.ArrayList> です。</span><span class="sxs-lookup"><span data-stu-id="1725e-103">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="1725e-104">構文</span><span class="sxs-lookup"><span data-stu-id="1725e-104">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="1725e-105">`ConnectionGroup.m_ConnectionList` フィールドはプライベートであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="1725e-105">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="1725e-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのフィールドの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1725e-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="1725e-107">要件</span><span class="sxs-lookup"><span data-stu-id="1725e-107">Requirements</span></span>

<span data-ttu-id="1725e-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="1725e-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="1725e-109">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="1725e-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="1725e-110">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1725e-110">**.NET Framework versions:** Available since 2.0.</span></span>
