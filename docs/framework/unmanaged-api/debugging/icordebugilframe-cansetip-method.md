---
title: ICorDebugILFrame::CanSetIP メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: 57d83d1f301cbfd43f8f553d9aef4beb3baf95f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131081"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="29a27-102">ICorDebugILFrame::CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="29a27-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="29a27-103">命令ポインターを Microsoft 中間言語 (MSIL) コード内の指定したオフセット位置に安全に設定できるかどうかを示す HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="29a27-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29a27-104">構文</span><span class="sxs-lookup"><span data-stu-id="29a27-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29a27-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29a27-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="29a27-106">から命令ポインターに必要な設定。</span><span class="sxs-lookup"><span data-stu-id="29a27-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29a27-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="29a27-107">Remarks</span></span>  
 <span data-ttu-id="29a27-108">`CanSetIP` メソッドを使用して、[次](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)のようにします。</span><span class="sxs-lookup"><span data-stu-id="29a27-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="29a27-109">`CanSetIP` が S_OK 以外の HRESULT を返す場合でも、`ICorDebugILFrame::SetIP`を呼び出すことはできますが、デバッガーがデバッグ中のコードの安全かつ適切な実行を継続する保証はありません。</span><span class="sxs-lookup"><span data-stu-id="29a27-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29a27-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="29a27-110">Requirements</span></span>  
 <span data-ttu-id="29a27-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29a27-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29a27-112">**ヘッダー:** CorDebug .idl、CorDebug、h</span><span class="sxs-lookup"><span data-stu-id="29a27-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="29a27-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29a27-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29a27-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29a27-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
