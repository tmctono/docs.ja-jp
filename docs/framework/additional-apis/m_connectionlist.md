---
title: 接続グループ.m_ConnectionList フィールド
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
ms.openlocfilehash: 8eb6f215c36e214f7095eeba90bf0aed66dfcea0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155851"
---
# <a name="connectiongroupm_connectionlist-field"></a><span data-ttu-id="34189-102">接続グループ.m\_接続リスト フィールド</span><span class="sxs-lookup"><span data-stu-id="34189-102">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="34189-103">`ConnectionGroup.m_ConnectionList`は、<xref:System.Collections.ArrayList>同じ URI を提供し、有効期限や認証などの他のプロパティで同じ値を共有する接続オブジェクトの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="34189-103">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="34189-104">構文</span><span class="sxs-lookup"><span data-stu-id="34189-104">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="34189-105">フィールド`ConnectionGroup.m_ConnectionList`はプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="34189-105">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="34189-106">マイクロソフトは、どのような状況においても、本稼動アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="34189-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="34189-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="34189-107">Requirements</span></span>

<span data-ttu-id="34189-108">**名前空間:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="34189-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="34189-109">**アセンブリ:** システム (システム.dll 内)</span><span class="sxs-lookup"><span data-stu-id="34189-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="34189-110">**.NET フレームワークのバージョン:** 2.0 以降で利用可能。</span><span class="sxs-lookup"><span data-stu-id="34189-110">**.NET Framework versions:** Available since 2.0.</span></span>
