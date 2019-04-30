---
title: ICorDebugNativeFrame::GetRegisterSet メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03a4f7ecc227679e6b0afa29b20de1aefeae3b76
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987871"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="4a68c-102">ICorDebugNativeFrame::GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="4a68c-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="4a68c-103">このスタック フレームのレジスタ セットを取得します。</span><span class="sxs-lookup"><span data-stu-id="4a68c-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a68c-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a68c-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a68c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a68c-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="4a68c-106">[out]アドレスへのポインター、 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)このスタック フレームの登録を表すオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="4a68c-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a68c-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a68c-107">Requirements</span></span>  
 <span data-ttu-id="4a68c-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a68c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a68c-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a68c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a68c-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a68c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a68c-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a68c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a68c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a68c-112">See also</span></span>
