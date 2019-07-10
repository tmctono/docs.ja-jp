---
title: ICorDebugThread4::GetBlockingObjects メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d83f9c0b187ad8b2955bc12ff168e0c4f26b909
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765230"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="9e98f-102">ICorDebugThread4::GetBlockingObjects メソッド</span><span class="sxs-lookup"><span data-stu-id="9e98f-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="9e98f-103">順序付けされた列挙体を提供[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)スレッドにブロックしている情報を提供する構造体。</span><span class="sxs-lookup"><span data-stu-id="9e98f-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e98f-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e98f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e98f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e98f-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="9e98f-106">[out]順序付けされた列挙体へのポインター [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="9e98f-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e98f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e98f-107">Remarks</span></span>  
 <span data-ttu-id="9e98f-108">返された列挙体の最初の要素は、スレッドをブロックしている最初の構造体に対応します。</span><span class="sxs-lookup"><span data-stu-id="9e98f-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="9e98f-109">2 番目の要素と、最初のブロックされたとき非同期プロシージャ コール (APC) の実行中に検出されるブロックしている項目に対応します。</span><span class="sxs-lookup"><span data-stu-id="9e98f-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="9e98f-110">列挙体は、現在の同期状態の期間に対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9e98f-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="9e98f-111">デバッグ対象が同期された状態では、このメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e98f-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="9e98f-112">場合`ppBlockingObjectEnum`有効なポインターでない、結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="9e98f-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="9e98f-113">スレッドがブロックされ、メソッドが失敗を示す HRESULT を返す、エラーを特定できない場合それ以外の場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="9e98f-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e98f-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e98f-114">Requirements</span></span>  
 <span data-ttu-id="9e98f-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e98f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e98f-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e98f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e98f-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e98f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e98f-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e98f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e98f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e98f-119">See also</span></span>

- [<span data-ttu-id="9e98f-120">ICorDebugThread4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e98f-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="9e98f-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e98f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9e98f-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9e98f-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
