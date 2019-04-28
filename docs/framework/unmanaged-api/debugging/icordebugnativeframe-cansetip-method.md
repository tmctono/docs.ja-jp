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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd16db8c009fe81f2674a8bf9c7ad3a2a4827777
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927349"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="bbb8b-102">ICorDebugNativeFrame::CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="bbb8b-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="bbb8b-103">命令ポインター (IP) をネイティブ コードで指定されたオフセット位置に設定しても安全でかどうかを示す HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="bbb8b-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbb8b-104">構文</span><span class="sxs-lookup"><span data-stu-id="bbb8b-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbb8b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bbb8b-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="bbb8b-106">[in]命令ポインターの必要な設定です。</span><span class="sxs-lookup"><span data-stu-id="bbb8b-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbb8b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="bbb8b-107">Remarks</span></span>  
 <span data-ttu-id="bbb8b-108">使用して、`CanSetIP`メソッドを呼び出す前に、 [icordebugnativeframe::setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="bbb8b-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="bbb8b-109">場合`CanSetIP`HRESULT を返します、S_OK 以外を呼び出すことができますも`ICorDebugNativeFrame::SetIP`デバッガーがデバッグ中のコードの安全かつ適切な実行を継続するという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="bbb8b-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbb8b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="bbb8b-110">Requirements</span></span>  
 <span data-ttu-id="bbb8b-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbb8b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbb8b-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbb8b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbb8b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbb8b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbb8b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbb8b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb8b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbb8b-115">See also</span></span>
