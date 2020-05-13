---
title: ICorDebugRegisterSet2::SetRegisters メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
ms.openlocfilehash: ebbd8dc2b715541850ed3b3bc530c0dd28993e1d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378125"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="654cf-102">ICorDebugRegisterSet2::SetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="654cf-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="654cf-103">`SetRegisters`は .NET Framework バージョン2.0 では実装されていません。</span><span class="sxs-lookup"><span data-stu-id="654cf-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="654cf-104">このメソッドは呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="654cf-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="654cf-105">「いいね!: [: setip](icordebugilframe-setip-method.md) 」や「いいね!: [: setip](icordebugnativeframe-setip-method.md)」などの上位レベルの操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="654cf-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="654cf-106">構文</span><span class="sxs-lookup"><span data-stu-id="654cf-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="654cf-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="654cf-107">Requirements</span></span>  
 <span data-ttu-id="654cf-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654cf-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="654cf-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="654cf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="654cf-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="654cf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="654cf-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="654cf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="654cf-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="654cf-112">See also</span></span>

- [<span data-ttu-id="654cf-113">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="654cf-113">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="654cf-114">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="654cf-114">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
