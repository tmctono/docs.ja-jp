---
title: ICorDebugRegisterSet::SetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: 8731b57206f7987efc2498a5abe62295cd1cfae5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131323"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="9a3d6-102">ICorDebugRegisterSet::SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="9a3d6-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="9a3d6-103">`SetThreadContext` は .NET Framework バージョン2.0 では実装されていません。</span><span class="sxs-lookup"><span data-stu-id="9a3d6-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="9a3d6-104">このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="9a3d6-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a3d6-105">スレッドのコンテキストを設定するには、高レベルの操作の[テキストフレーム:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9a3d6-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a3d6-106">構文</span><span class="sxs-lookup"><span data-stu-id="9a3d6-106">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="9a3d6-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="9a3d6-107">Requirements</span></span>  
 <span data-ttu-id="9a3d6-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a3d6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a3d6-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a3d6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a3d6-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a3d6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a3d6-111">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="9a3d6-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a3d6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a3d6-112">See also</span></span>

- [<span data-ttu-id="9a3d6-113">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a3d6-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="9a3d6-114">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a3d6-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
