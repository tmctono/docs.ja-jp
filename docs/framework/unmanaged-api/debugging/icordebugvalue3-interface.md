---
title: ICorDebugValue3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 9f521eb942f37b8cf1d00bcc672071a69692b876
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396645"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="da645-102">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da645-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="da645-103">"ICorDebugValue" インターフェイスと "ICorDebugValue2" インターフェイスを拡張して、2 GB を超える配列のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="da645-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da645-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="da645-104">Methods</span></span>  
  
|<span data-ttu-id="da645-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="da645-105">Method</span></span>|<span data-ttu-id="da645-106">説明</span><span class="sxs-lookup"><span data-stu-id="da645-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da645-107">GetSize64 メソッド</span><span class="sxs-lookup"><span data-stu-id="da645-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="da645-108">このオブジェクトのサイズ (バイト単位) を取得し `ICorDebugValue3` ます。</span><span class="sxs-lookup"><span data-stu-id="da645-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da645-109">解説</span><span class="sxs-lookup"><span data-stu-id="da645-109">Remarks</span></span>  
 <span data-ttu-id="da645-110">[ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md)メソッドは、0 ~ 2147483647 バイトの範囲のオブジェクトサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="da645-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="da645-111">.NET Framework 4.5 では、配列のサイズが 2 GB を超える場合があります。</span><span class="sxs-lookup"><span data-stu-id="da645-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="da645-112">`ICorDebugValue3`インターフェイスを使用すると、これらの配列のサイズを決定できます。</span><span class="sxs-lookup"><span data-stu-id="da645-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da645-113">要件</span><span class="sxs-lookup"><span data-stu-id="da645-113">Requirements</span></span>  
 <span data-ttu-id="da645-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da645-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da645-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da645-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da645-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da645-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da645-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da645-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da645-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="da645-118">See also</span></span>

- [<span data-ttu-id="da645-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="da645-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="da645-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="da645-120">Debugging</span></span>](index.md)
