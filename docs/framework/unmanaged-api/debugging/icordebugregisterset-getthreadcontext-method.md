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
ms.openlocfilehash: db4f9bc6277015055cbcdb509628f2862a71dbc4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127154"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="66657-102">ICorDebugRegisterSet::GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="66657-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="66657-103">現在のスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="66657-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66657-104">構文</span><span class="sxs-lookup"><span data-stu-id="66657-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66657-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66657-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="66657-106">から`context` 配列のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="66657-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="66657-107">[入力、出力]現在のプラットフォームの Win32 `CONTEXT` 構造体を構成するバイト配列。</span><span class="sxs-lookup"><span data-stu-id="66657-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66657-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="66657-108">Remarks</span></span>  
 <span data-ttu-id="66657-109">スレッドが一時的に変更されている "ハイジャック" 状態である可能性があるため、デバッガーは Win32 `GetThreadContext` 関数の代わりにこの関数を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="66657-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="66657-110">返されるデータは、現在のプラットフォームの Win32 `CONTEXT` 構造体です。</span><span class="sxs-lookup"><span data-stu-id="66657-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="66657-111">非リーフフレームの場合、クライアントは、テキストボックス[:: GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)を使用して、どのレジスタが有効であるかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66657-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66657-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="66657-112">Requirements</span></span>  
 <span data-ttu-id="66657-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66657-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66657-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66657-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66657-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66657-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66657-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66657-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66657-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="66657-117">See also</span></span>

- [<span data-ttu-id="66657-118">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66657-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="66657-119">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66657-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
