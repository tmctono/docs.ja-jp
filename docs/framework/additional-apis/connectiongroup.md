---
title: ConnectionGroup クラス
description: ConnectionGroup クラスについて説明します。このクラスは、ServicePoint コンテキスト内で接続をグループ化し、.NET のネットワークリソースのコンテキストを維持するために使用されます。
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 25c08217-fdeb-44b9-9cd6-1b4955d6e602
ms.openlocfilehash: 7121713b26880f2490b40d59d92d431a567519b3
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989817"
---
# <a name="connectiongroup-class"></a><span data-ttu-id="277a7-103">ConnectionGroup クラス</span><span class="sxs-lookup"><span data-stu-id="277a7-103">ConnectionGroup Class</span></span>

<span data-ttu-id="277a7-104">クラスは、 `ConnectionGroup` コンテキスト内の接続の一覧をグループ化 <xref:System.Net.ServicePoint> し、ネットワークリソース (プロキシや個別のクライアントなど) のコンテキストを維持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="277a7-104">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="277a7-105">構文</span><span class="sxs-lookup"><span data-stu-id="277a7-105">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="277a7-106">`ConnectionGroup`クラスは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="277a7-106">The `ConnectionGroup` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="277a7-107">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="277a7-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="277a7-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="277a7-108">Requirements</span></span>

<span data-ttu-id="277a7-109">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="277a7-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="277a7-110">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="277a7-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="277a7-111">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="277a7-111">**.NET Framework versions:** Available since 2.0.</span></span>
