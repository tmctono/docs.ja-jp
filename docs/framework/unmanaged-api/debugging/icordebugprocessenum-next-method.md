---
title: ICorDebugProcessEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: d00a5f71ac7e47d78deebca0e46350e465964c72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210099"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="eb136-102">ICorDebugProcessEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="eb136-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="eb136-103">現在の位置から開始して、指定された数の処理インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="eb136-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb136-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb136-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb136-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb136-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="eb136-106">から`ICorDebugProcess`取得するインスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="eb136-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="eb136-107">入出力ポインターの配列。各ポインターは、 `ICorDebugProcess` プロセスを表すオブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="eb136-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="eb136-108">入出力実際に返されたインスタンスの数へのポインター `ICorDebugProcess` 。</span><span class="sxs-lookup"><span data-stu-id="eb136-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="eb136-109">が1の場合、この値は null `celt` になります。</span><span class="sxs-lookup"><span data-stu-id="eb136-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb136-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="eb136-110">Requirements</span></span>  
 <span data-ttu-id="eb136-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb136-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb136-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb136-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb136-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb136-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb136-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb136-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
