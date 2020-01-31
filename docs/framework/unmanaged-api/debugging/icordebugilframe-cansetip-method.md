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
ms.openlocfilehash: c6a02b080739d00667893008be4a19b4fa9a6ef2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788590"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="51b0b-102">ICorDebugILFrame::CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="51b0b-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="51b0b-103">命令ポインターを Microsoft 中間言語 (MSIL) コード内の指定したオフセット位置に安全に設定できるかどうかを示す HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="51b0b-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51b0b-104">構文</span><span class="sxs-lookup"><span data-stu-id="51b0b-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51b0b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="51b0b-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="51b0b-106">から命令ポインターに必要な設定。</span><span class="sxs-lookup"><span data-stu-id="51b0b-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51b0b-107">コメント</span><span class="sxs-lookup"><span data-stu-id="51b0b-107">Remarks</span></span>  
 <span data-ttu-id="51b0b-108">`CanSetIP` メソッドを使用して、[次](icordebugilframe-setip-method.md)のようにします。</span><span class="sxs-lookup"><span data-stu-id="51b0b-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="51b0b-109">`CanSetIP` が S_OK 以外の HRESULT を返す場合でも `ICorDebugILFrame::SetIP`を呼び出すことはできますが、デバッガーがデバッグ中のコードの安全かつ適切な実行を継続するという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="51b0b-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51b0b-110">要件</span><span class="sxs-lookup"><span data-stu-id="51b0b-110">Requirements</span></span>  
 <span data-ttu-id="51b0b-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51b0b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51b0b-112">**ヘッダー:** CorDebug .idl、CorDebug、h</span><span class="sxs-lookup"><span data-stu-id="51b0b-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="51b0b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51b0b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51b0b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51b0b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
