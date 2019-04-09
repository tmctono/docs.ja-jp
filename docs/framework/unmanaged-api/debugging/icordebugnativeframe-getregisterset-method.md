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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077928"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="1bfbc-102">ICorDebugNativeFrame::GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="1bfbc-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="1bfbc-103">このスタック フレームのレジスタ セットを取得します。</span><span class="sxs-lookup"><span data-stu-id="1bfbc-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bfbc-104">構文</span><span class="sxs-lookup"><span data-stu-id="1bfbc-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bfbc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1bfbc-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="1bfbc-106">[out]アドレスへのポインター、 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)このスタック フレームの登録を表すオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="1bfbc-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bfbc-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="1bfbc-107">Requirements</span></span>  
 <span data-ttu-id="1bfbc-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bfbc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bfbc-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bfbc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bfbc-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bfbc-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1bfbc-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="1bfbc-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1bfbc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bfbc-112">See also</span></span>
