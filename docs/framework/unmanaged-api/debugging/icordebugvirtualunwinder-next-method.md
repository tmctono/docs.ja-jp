---
title: Icordebugvirtualunwinder::next メソッド
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74be827dc97213507b96da9e025923f859011acd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076888"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="3686d-102">Icordebugvirtualunwinder::next メソッド</span><span class="sxs-lookup"><span data-stu-id="3686d-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="3686d-103">呼び出し元のコンテキストに進みます。</span><span class="sxs-lookup"><span data-stu-id="3686d-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3686d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3686d-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="3686d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3686d-105">Parameters</span></span>  
 <span data-ttu-id="3686d-106">なし。</span><span class="sxs-lookup"><span data-stu-id="3686d-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3686d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3686d-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="3686d-108">正常にアンワインドが発生した場合または`CORDBG_S_AT_END_OF_STACK`フレームがあるため、アンワインドを完了できない場合。</span><span class="sxs-lookup"><span data-stu-id="3686d-108">if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="3686d-109">失敗を示す HRESULT が返される場合、ICorDebug API は `CORDBG_E_DATA_TARGET_ERROR` を返します。</span><span class="sxs-lookup"><span data-stu-id="3686d-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3686d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3686d-110">Remarks</span></span>  
 <span data-ttu-id="3686d-111">スタック ウォーカーにより、前へ進んでいることが確認されます。これにより、最終的に `Next` の呼び出しによって、失敗を示す HRESULT または `CORDBG_S_AT_END_OF_STACK` が返されます。</span><span class="sxs-lookup"><span data-stu-id="3686d-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="3686d-112">返す`S_OK`無期限に無限ループが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3686d-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3686d-113">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3686d-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3686d-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="3686d-114">Requirements</span></span>  
 <span data-ttu-id="3686d-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3686d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3686d-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3686d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3686d-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3686d-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3686d-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3686d-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3686d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="3686d-119">See also</span></span>

- [<span data-ttu-id="3686d-120">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3686d-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="3686d-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3686d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
