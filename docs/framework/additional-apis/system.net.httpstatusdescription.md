---
title: HttpStatusDescription クラス (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990543"
---
# <a name="httpstatusdescription-class"></a><span data-ttu-id="9c531-102">HttpStatusDescription クラス</span><span class="sxs-lookup"><span data-stu-id="9c531-102">HttpStatusDescription class</span></span>

<span data-ttu-id="9c531-103">標準の HTTP 状態の説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="9c531-103">Provides standard HTTP status descriptions.</span></span> <span data-ttu-id="9c531-104">このクラスは継承できません。</span><span class="sxs-lookup"><span data-stu-id="9c531-104">This class cannot be inherited.</span></span>

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> <span data-ttu-id="9c531-105">このクラスは内部的なものであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="9c531-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="9c531-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c531-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="get-method"></a><span data-ttu-id="9c531-107">Get メソッド</span><span class="sxs-lookup"><span data-stu-id="9c531-107">Get method</span></span>

<span data-ttu-id="9c531-108">指定された HTTP ステータスコードに関連付けられている説明を返します。</span><span class="sxs-lookup"><span data-stu-id="9c531-108">Returns the description associated with the specified HTTP status code.</span></span>

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a><span data-ttu-id="9c531-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9c531-109">Parameters</span></span>

<span data-ttu-id="9c531-110">`code` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="9c531-110">`code` <xref:System.Int32></span></span>

<span data-ttu-id="9c531-111">HTTP 状態コード (など) `404` 。</span><span class="sxs-lookup"><span data-stu-id="9c531-111">The HTTP status code, for example, `404`.</span></span>

### <a name="return-value"></a><span data-ttu-id="9c531-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="9c531-112">Return value</span></span>

<xref:System.String?displayProperty=nameWithType>

<span data-ttu-id="9c531-113">HTTP 状態の説明。</span><span class="sxs-lookup"><span data-stu-id="9c531-113">The HTTP status description.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c531-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="9c531-114">Requirements</span></span>

<span data-ttu-id="9c531-115">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="9c531-115">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="9c531-116">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="9c531-116">**Assembly:** System (in System.dll)</span></span>
