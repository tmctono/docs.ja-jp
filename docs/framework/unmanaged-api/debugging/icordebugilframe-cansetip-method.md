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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49cef22e88613fe4c4dfb3fb35a92977977b1827
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988638"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="cb42d-102">ICorDebugILFrame::CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="cb42d-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="cb42d-103">命令ポインターを Microsoft 中間言語 (MSIL) コードで指定されたオフセット位置に設定しても安全でかどうかを示す HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb42d-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb42d-104">構文</span><span class="sxs-lookup"><span data-stu-id="cb42d-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb42d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb42d-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="cb42d-106">[in]命令ポインターの必要な設定です。</span><span class="sxs-lookup"><span data-stu-id="cb42d-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb42d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb42d-107">Remarks</span></span>  
 <span data-ttu-id="cb42d-108">使用して、`CanSetIP`メソッドを呼び出す前に、 [icordebugilframe::setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cb42d-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="cb42d-109">場合`CanSetIP`HRESULT を返します、S_OK 以外を呼び出すことができますも`ICorDebugILFrame::SetIP`デバッガーがデバッグ中のコードの安全かつ適切な実行を継続するという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="cb42d-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb42d-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="cb42d-110">Requirements</span></span>  
 <span data-ttu-id="cb42d-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb42d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb42d-112">**ヘッダー:** CorDebug.idl, CorDebug,h</span><span class="sxs-lookup"><span data-stu-id="cb42d-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="cb42d-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb42d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb42d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb42d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
