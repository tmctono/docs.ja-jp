---
title: ICorDebugDataTarget::GetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 278320391615eddaa8ba878ef87f802f30cddb95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122022"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="7d499-102">ICorDebugDataTarget::GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="7d499-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="7d499-103">指定されたスレッドの現在のスレッドコンテキストを返します。</span><span class="sxs-lookup"><span data-stu-id="7d499-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d499-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d499-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d499-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d499-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="7d499-106">からコンテキストを取得するスレッドの識別子。</span><span class="sxs-lookup"><span data-stu-id="7d499-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="7d499-107">識別子はオペレーティングシステムによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="7d499-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="7d499-108">からコンテキストのどの部分を読み取る必要があるかを示す、プラットフォームに依存するフラグのビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="7d499-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="7d499-109">[入力] `pContext` のサイズ。</span><span class="sxs-lookup"><span data-stu-id="7d499-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="7d499-110">入出力スレッドコンテキストが格納されるバッファー。</span><span class="sxs-lookup"><span data-stu-id="7d499-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d499-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d499-111">Remarks</span></span>  
 <span data-ttu-id="7d499-112">Windows プラットフォームでは、`pContext` は、の `CONTEXT` 構造 (Winnt.h で定義されています) である必要があります。これは[、のコンピューター](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)の種類に対応しています。</span><span class="sxs-lookup"><span data-stu-id="7d499-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="7d499-113">`contextFlags` には、`CONTEXT` 構造体の `ContextFlags` フィールドと同じ値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d499-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="7d499-114">`CONTEXT` 構造体はプロセッサに固有です。詳細については、「Winnt.h ファイル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d499-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d499-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="7d499-115">Requirements</span></span>  
 <span data-ttu-id="7d499-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d499-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d499-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d499-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d499-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d499-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d499-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d499-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d499-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d499-120">See also</span></span>

- [<span data-ttu-id="7d499-121">ICorDebugDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d499-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="7d499-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d499-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7d499-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="7d499-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
