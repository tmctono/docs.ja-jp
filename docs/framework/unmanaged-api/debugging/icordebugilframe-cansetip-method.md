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
ms.openlocfilehash: 2bd4ab4a080461c56b0287d24aa288847445d803
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210320"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="cfd64-102">ICorDebugILFrame::CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="cfd64-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="cfd64-103">命令ポインターを Microsoft 中間言語 (MSIL) コード内の指定したオフセット位置に安全に設定できるかどうかを示す HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfd64-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfd64-104">構文</span><span class="sxs-lookup"><span data-stu-id="cfd64-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfd64-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfd64-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="cfd64-106">から命令ポインターに必要な設定。</span><span class="sxs-lookup"><span data-stu-id="cfd64-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfd64-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cfd64-107">Remarks</span></span>  
 <span data-ttu-id="cfd64-108">次のように、メソッドを使用します。 `CanSetIP` [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md)</span><span class="sxs-lookup"><span data-stu-id="cfd64-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="cfd64-109">が `CanSetIP` S_OK 以外の HRESULT を返した場合でもを呼び出すことはでき `ICorDebugILFrame::SetIP` ますが、デバッガーがデバッグ中のコードの安全かつ適切な実行を継続する保証はありません。</span><span class="sxs-lookup"><span data-stu-id="cfd64-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfd64-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="cfd64-110">Requirements</span></span>  
 <span data-ttu-id="cfd64-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd64-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfd64-112">**ヘッダー:** CorDebug .idl、CorDebug、h</span><span class="sxs-lookup"><span data-stu-id="cfd64-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="cfd64-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfd64-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfd64-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfd64-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
