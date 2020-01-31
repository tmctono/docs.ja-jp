---
title: ICorDebugRegisterSet::SetRegisters メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
ms.openlocfilehash: d61d37448930d451b519c93909165e5e16f92765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792050"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="dc3bb-102">ICorDebugRegisterSet::SetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="dc3bb-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="dc3bb-103">`SetRegisters` は .NET Framework バージョン2.0 では実装されていません。</span><span class="sxs-lookup"><span data-stu-id="dc3bb-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="dc3bb-104">このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="dc3bb-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc3bb-105">「いいね!: [: setip](icordebugilframe-setip-method.md) 」や「いいね!: [: setip](icordebugnativeframe-setip-method.md)」などの上位レベルの操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc3bb-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc3bb-106">構文</span><span class="sxs-lookup"><span data-stu-id="dc3bb-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="dc3bb-107">要件</span><span class="sxs-lookup"><span data-stu-id="dc3bb-107">Requirements</span></span>  
 <span data-ttu-id="dc3bb-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc3bb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc3bb-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc3bb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc3bb-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc3bb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc3bb-111">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="dc3bb-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc3bb-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc3bb-112">See also</span></span>

- [<span data-ttu-id="dc3bb-113">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc3bb-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="dc3bb-114">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc3bb-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
