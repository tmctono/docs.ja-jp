---
title: 接続.m_WriteListフィールド
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
ms.openlocfilehash: 6c60831ddf23ce8ac9afcf244383d24732c3ef8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155838"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="50989-102">接続.m\_書き込みリスト フィールド</span><span class="sxs-lookup"><span data-stu-id="50989-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="50989-103">`Connection.m_WriteList`は、HTTP<xref:System.Net.HttpWebRequest>経由で<xref:System.Collections.ArrayList>送信されるキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="50989-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="50989-104">構文</span><span class="sxs-lookup"><span data-stu-id="50989-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="50989-105">フィールド`Connection.m_WriteList`はプライベートであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="50989-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="50989-106">マイクロソフトは、どのような状況においても、本稼動アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="50989-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="50989-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="50989-107">Requirements</span></span>

<span data-ttu-id="50989-108">**名前空間:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="50989-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="50989-109">**アセンブリ:** システム (システム.dll 内)</span><span class="sxs-lookup"><span data-stu-id="50989-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="50989-110">**.NET フレームワークのバージョン:** 2.0 以降で利用可能。</span><span class="sxs-lookup"><span data-stu-id="50989-110">**.NET Framework versions:** Available since 2.0.</span></span>
