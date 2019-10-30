---
title: ICorDebugNativeFrame::CanSetIP メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: b3758ac1a84092b8bf2678f9cc2c19c9d9961690
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137322"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="0a356-102">ICorDebugNativeFrame::CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="0a356-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="0a356-103">命令ポインター (IP) をネイティブコード内の指定されたオフセット位置に安全に設定できるかどうかを示す HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="0a356-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a356-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a356-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a356-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a356-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="0a356-106">から命令ポインターに必要な設定。</span><span class="sxs-lookup"><span data-stu-id="0a356-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a356-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0a356-107">Remarks</span></span>  
 <span data-ttu-id="0a356-108">`CanSetIP` メソッドを使用して、このメソッドを[実行](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="0a356-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="0a356-109">`CanSetIP` が S_OK 以外の HRESULT を返す場合でも、`ICorDebugNativeFrame::SetIP`を呼び出すことはできますが、デバッガーがデバッグ中のコードの安全かつ適切な実行を継続する保証はありません。</span><span class="sxs-lookup"><span data-stu-id="0a356-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a356-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="0a356-110">Requirements</span></span>  
 <span data-ttu-id="0a356-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a356-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a356-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a356-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a356-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a356-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a356-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a356-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a356-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a356-115">See also</span></span>
