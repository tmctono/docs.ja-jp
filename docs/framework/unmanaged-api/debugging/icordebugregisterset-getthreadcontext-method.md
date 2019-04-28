---
title: ICorDebugRegisterSet::GetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fecbcff0fd124b94aeeecf82e23d9875c34ebb9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782910"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="f7745-102">ICorDebugRegisterSet::GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="f7745-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="f7745-103">現在のスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7745-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7745-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7745-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7745-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7745-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="f7745-106">[in]サイズ (バイト単位) の`context`配列。</span><span class="sxs-lookup"><span data-stu-id="f7745-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="f7745-107">[入力、出力]Win32 を構成するバイトの配列`CONTEXT`現在のプラットフォームの構造体。</span><span class="sxs-lookup"><span data-stu-id="f7745-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7745-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f7745-108">Remarks</span></span>  
 <span data-ttu-id="f7745-109">デバッガーは、Win32 ではなく、この関数を呼び出す必要があります`GetThreadContext`関数は、スレッドのコンテキストに一時的に変更がされている「ハイジャック」の状態になるためです。</span><span class="sxs-lookup"><span data-stu-id="f7745-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="f7745-110">返されるデータは、Win32`CONTEXT`現在のプラットフォームの構造体。</span><span class="sxs-lookup"><span data-stu-id="f7745-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="f7745-111">使用してレジスタが有効なリーフ以外のフレームのクライアントを確認する必要があります[icordebugregisterset::getregistersavailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7745-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7745-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="f7745-112">Requirements</span></span>  
 <span data-ttu-id="f7745-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7745-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7745-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7745-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7745-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7745-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7745-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7745-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7745-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7745-117">See also</span></span>

- [<span data-ttu-id="f7745-118">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7745-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="f7745-119">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7745-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
