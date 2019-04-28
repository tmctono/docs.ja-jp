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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b1ea34c187de99d23b05b5e1a30c53bc54a6c0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782799"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="da378-102">ICorDebugRegisterSet::SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="da378-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="da378-103">`SetThreadContext` .NET Framework version 2.0 では実装されていません。</span><span class="sxs-lookup"><span data-stu-id="da378-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="da378-104">このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="da378-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da378-105">高度な操作を使用して[icordebugnativeframe::setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)スレッドのコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="da378-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da378-106">構文</span><span class="sxs-lookup"><span data-stu-id="da378-106">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="da378-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="da378-107">Requirements</span></span>  
 <span data-ttu-id="da378-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="da378-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da378-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da378-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da378-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da378-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da378-111">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="da378-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da378-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="da378-112">See also</span></span>

- [<span data-ttu-id="da378-113">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da378-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="da378-114">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da378-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
