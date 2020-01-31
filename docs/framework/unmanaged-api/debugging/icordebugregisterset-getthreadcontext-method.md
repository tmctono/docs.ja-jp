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
ms.openlocfilehash: 8137d5477b75b864e223852cf524ac8c5b6c0f2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792088"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="ebf33-102">ICorDebugRegisterSet::GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="ebf33-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="ebf33-103">現在のスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="ebf33-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf33-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebf33-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebf33-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ebf33-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="ebf33-106">から`context` 配列のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ebf33-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="ebf33-107">[入力、出力]現在のプラットフォームの Win32 `CONTEXT` 構造体を構成するバイト配列。</span><span class="sxs-lookup"><span data-stu-id="ebf33-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebf33-108">コメント</span><span class="sxs-lookup"><span data-stu-id="ebf33-108">Remarks</span></span>  
 <span data-ttu-id="ebf33-109">スレッドが一時的に変更されている "ハイジャック" 状態である可能性があるため、デバッガーは Win32 `GetThreadContext` 関数の代わりにこの関数を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebf33-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="ebf33-110">返されるデータは、現在のプラットフォームの Win32 `CONTEXT` 構造体です。</span><span class="sxs-lookup"><span data-stu-id="ebf33-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="ebf33-111">非リーフフレームの場合、クライアントは、テキストボックス[:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)を使用して、どのレジスタが有効であるかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebf33-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebf33-112">要件</span><span class="sxs-lookup"><span data-stu-id="ebf33-112">Requirements</span></span>  
 <span data-ttu-id="ebf33-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf33-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf33-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebf33-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebf33-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebf33-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebf33-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf33-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf33-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebf33-117">See also</span></span>

- [<span data-ttu-id="ebf33-118">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ebf33-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="ebf33-119">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ebf33-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
