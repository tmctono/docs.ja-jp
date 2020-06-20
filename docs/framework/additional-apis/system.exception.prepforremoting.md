---
title: PrepForRemoting メソッド (System)
description: .NET で PrepForRemoting メソッドを確認します。 メソッドは、クライアントで例外が再スローされる前に、サーバー側のスタックトレースをメッセージに追加します。
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105257"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="bc7c7-104">Exception.PrepForRemoting メソッド</span><span class="sxs-lookup"><span data-stu-id="bc7c7-104">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="bc7c7-105">クライアント呼び出しサイトで例外が再スローされる前に、サーバー側スタックトレースをメッセージに追加して保存します。</span><span class="sxs-lookup"><span data-stu-id="bc7c7-105">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="bc7c7-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="bc7c7-106">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="bc7c7-107">この <xref:System.Exception> インスタンス。</span><span class="sxs-lookup"><span data-stu-id="bc7c7-107">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc7c7-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="bc7c7-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="bc7c7-109">`Exception.PrepForRemoting`メソッドは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="bc7c7-109">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="bc7c7-110">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bc7c7-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="bc7c7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="bc7c7-111">Requirements</span></span>

<span data-ttu-id="bc7c7-112">**名前空間:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="bc7c7-112">**Namespace:** <xref:System></span></span>

<span data-ttu-id="bc7c7-113">**アセンブリ:** mscorlib.dll (mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="bc7c7-113">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="bc7c7-114">**.NET Framework のバージョン:** 1.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc7c7-114">**.NET Framework versions:** Available since 1.0.</span></span>
