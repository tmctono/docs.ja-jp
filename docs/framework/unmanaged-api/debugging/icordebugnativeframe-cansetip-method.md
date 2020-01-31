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
ms.openlocfilehash: d266ec7f82d7d4c7c66f137aafc1c8865d6f8889
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792802"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="c11da-102">ICorDebugNativeFrame::CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="c11da-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="c11da-103">命令ポインター (IP) をネイティブコード内の指定されたオフセット位置に安全に設定できるかどうかを示す HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="c11da-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c11da-104">構文</span><span class="sxs-lookup"><span data-stu-id="c11da-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c11da-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c11da-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="c11da-106">から命令ポインターに必要な設定。</span><span class="sxs-lookup"><span data-stu-id="c11da-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c11da-107">コメント</span><span class="sxs-lookup"><span data-stu-id="c11da-107">Remarks</span></span>  
 <span data-ttu-id="c11da-108">`CanSetIP` メソッドを使用して、このメソッドを[実行](icordebugnativeframe-setip-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="c11da-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="c11da-109">`CanSetIP` が S_OK 以外の HRESULT を返す場合でも `ICorDebugNativeFrame::SetIP`を呼び出すことはできますが、デバッガーがデバッグ中のコードの安全かつ適切な実行を継続するという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="c11da-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c11da-110">要件</span><span class="sxs-lookup"><span data-stu-id="c11da-110">Requirements</span></span>  
 <span data-ttu-id="c11da-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11da-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c11da-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c11da-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c11da-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c11da-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c11da-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c11da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c11da-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c11da-115">See also</span></span>
