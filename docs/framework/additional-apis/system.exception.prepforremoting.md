---
title: PrepForRemoting メソッド (System)
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214895"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="73509-102">Exception.PrepForRemoting メソッド</span><span class="sxs-lookup"><span data-stu-id="73509-102">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="73509-103">クライアント呼び出しサイトで例外が再スローされる前に、サーバー側スタックトレースをメッセージに追加して保存します。</span><span class="sxs-lookup"><span data-stu-id="73509-103">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="73509-104">戻り値</span><span class="sxs-lookup"><span data-stu-id="73509-104">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="73509-105">この <xref:System.Exception> インスタンス。</span><span class="sxs-lookup"><span data-stu-id="73509-105">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="73509-106">コメント</span><span class="sxs-lookup"><span data-stu-id="73509-106">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="73509-107">`Exception.PrepForRemoting` メソッドは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="73509-107">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="73509-108">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="73509-108">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="73509-109">要件</span><span class="sxs-lookup"><span data-stu-id="73509-109">Requirements</span></span>

<span data-ttu-id="73509-110">**名前空間:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="73509-110">**Namespace:** <xref:System></span></span>

<span data-ttu-id="73509-111">**アセンブリ:** mscorlib.dll (mscorlib.dll 内)</span><span class="sxs-lookup"><span data-stu-id="73509-111">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="73509-112">**.NET Framework のバージョン:** 1.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="73509-112">**.NET Framework versions:** Available since 1.0.</span></span>
