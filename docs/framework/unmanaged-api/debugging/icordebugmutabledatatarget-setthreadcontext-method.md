---
title: ICorDebugMutableDataTarget::SetThreadContext メソッド
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6629af393eeadb68292f8f2360ecb60c09a0cd03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764616"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="ac74f-102">ICorDebugMutableDataTarget::SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="ac74f-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="ac74f-103">スレッドのコンテキスト (レジスタの値) を設定します。</span><span class="sxs-lookup"><span data-stu-id="ac74f-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac74f-104">構文</span><span class="sxs-lookup"><span data-stu-id="ac74f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac74f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac74f-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="ac74f-106">[in] オペレーティング システム定義のスレッド識別子。</span><span class="sxs-lookup"><span data-stu-id="ac74f-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="ac74f-107">[in]書き込まれる `pContext` バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="ac74f-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="ac74f-108">[in]書き込まれるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ac74f-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac74f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac74f-109">Remarks</span></span>  
 <span data-ttu-id="ac74f-110">`SetThreadContext` メソッドは、オペレーティング システム定義の `dwThreadID` 引数で指定されるスレッドの現在のコンテキストを更新します。</span><span class="sxs-lookup"><span data-stu-id="ac74f-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="ac74f-111">コンテキスト レコードの形式はにより示されるプラットフォームによって決まります、 [icordebugdatatarget::getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ac74f-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="ac74f-112">これは、Windows、[コンテキスト](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context)構造体。</span><span class="sxs-lookup"><span data-stu-id="ac74f-112">On Windows, this is a [CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac74f-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="ac74f-113">Requirements</span></span>  
 <span data-ttu-id="ac74f-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac74f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac74f-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac74f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac74f-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac74f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac74f-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac74f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac74f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac74f-118">See also</span></span>

- [<span data-ttu-id="ac74f-119">ICorDebugMutableDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac74f-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="ac74f-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac74f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
