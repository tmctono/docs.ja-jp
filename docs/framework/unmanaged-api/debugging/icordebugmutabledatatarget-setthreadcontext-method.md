---
title: ICorDebugMutableDataTarget::SetThreadContext メソッド
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21a24b3ae3563db09f1f7e9229f388abf8de654c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038308"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="ca00b-102">ICorDebugMutableDataTarget::SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="ca00b-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="ca00b-103">スレッドのコンテキスト (レジスタの値) を設定します。</span><span class="sxs-lookup"><span data-stu-id="ca00b-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca00b-104">構文</span><span class="sxs-lookup"><span data-stu-id="ca00b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca00b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ca00b-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="ca00b-106">[in] オペレーティング システム定義のスレッド識別子。</span><span class="sxs-lookup"><span data-stu-id="ca00b-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="ca00b-107">[in]書き込まれる `pContext` バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="ca00b-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="ca00b-108">[in]書き込まれるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ca00b-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca00b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca00b-109">Remarks</span></span>  
 <span data-ttu-id="ca00b-110">`SetThreadContext` メソッドは、オペレーティング システム定義の `dwThreadID` 引数で指定されるスレッドの現在のコンテキストを更新します。</span><span class="sxs-lookup"><span data-stu-id="ca00b-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="ca00b-111">コンテキストレコードの形式は、のプラットフォームによって決定されます。このプラットフォームでは、次[のように](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)指定します。</span><span class="sxs-lookup"><span data-stu-id="ca00b-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="ca00b-112">Windows では、これは[コンテキスト](/windows/win32/api/winnt/ns-winnt-arm64_nt_context)構造です。</span><span class="sxs-lookup"><span data-stu-id="ca00b-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca00b-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="ca00b-113">Requirements</span></span>  
 <span data-ttu-id="ca00b-114">**・**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca00b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca00b-115">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ca00b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca00b-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="ca00b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca00b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca00b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca00b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca00b-118">See also</span></span>

- [<span data-ttu-id="ca00b-119">ICorDebugMutableDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca00b-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="ca00b-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca00b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
