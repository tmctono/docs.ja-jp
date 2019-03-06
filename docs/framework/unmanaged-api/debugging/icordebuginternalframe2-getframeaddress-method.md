---
title: ICorDebugInternalFrame2::GetFrameAddress メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3293c3b0d5fa4615c351949afdb1acf8cd560b5e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480716"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="4603e-102">ICorDebugInternalFrame2::GetFrameAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="4603e-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="4603e-103">内部フレームのスタック アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="4603e-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4603e-104">構文</span><span class="sxs-lookup"><span data-stu-id="4603e-104">Syntax</span></span>  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4603e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4603e-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="4603e-106">[out]ポインター、`CORDB_ADDRESS`内部フレーム。</span><span class="sxs-lookup"><span data-stu-id="4603e-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4603e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4603e-107">Return Value</span></span>  
 <span data-ttu-id="4603e-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="4603e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4603e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4603e-109">HRESULT</span></span>|<span data-ttu-id="4603e-110">説明</span><span class="sxs-lookup"><span data-stu-id="4603e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4603e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4603e-111">S_OK</span></span>|<span data-ttu-id="4603e-112">内部フレームのアドレスが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4603e-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="4603e-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4603e-113">E_FAIL</span></span>|<span data-ttu-id="4603e-114">内部フレームのアドレスは返されませんでした。</span><span class="sxs-lookup"><span data-stu-id="4603e-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="4603e-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4603e-115">E_INVALIDARG</span></span>|<span data-ttu-id="4603e-116">`pAddress` は `null` です。</span><span class="sxs-lookup"><span data-stu-id="4603e-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4603e-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="4603e-117">Remarks</span></span>  
 <span data-ttu-id="4603e-118">戻り値`pAddress`スタック上の他のフレームの基準とした内部フレームの場所を特定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="4603e-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="4603e-119">IA 64 ベースのコンピューター上でも内部フレームはのみ、スタック上に存在して、バッキング ストアへの対応するポインターはありません。</span><span class="sxs-lookup"><span data-stu-id="4603e-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4603e-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="4603e-120">Requirements</span></span>  
 <span data-ttu-id="4603e-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4603e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4603e-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4603e-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4603e-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4603e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4603e-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4603e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4603e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4603e-125">See also</span></span>
- [<span data-ttu-id="4603e-126">ICorDebugInternalFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4603e-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="4603e-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4603e-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4603e-128">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4603e-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
