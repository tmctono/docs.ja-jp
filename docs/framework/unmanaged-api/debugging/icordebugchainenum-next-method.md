---
title: ICorDebugChainEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
ms.openlocfilehash: 2d075820df534e08bdf4c2b75d36f6a60f979662
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894096"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="e1736-102">ICorDebugChainEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="e1736-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="e1736-103">現在の位置から開始して、指定された数の値を列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="e1736-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1736-104">構文</span><span class="sxs-lookup"><span data-stu-id="e1736-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1736-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e1736-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e1736-106">から取得するインスタンス`ICorDebugChain`の数。</span><span class="sxs-lookup"><span data-stu-id="e1736-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="e1736-107">入出力ポインターの配列。各ポインターは、チェーンを表す`ICorDebugChain`オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="e1736-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e1736-108">入出力実際に返されたインスタンス`ICorDebugChain`の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e1736-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="e1736-109">が1の場合`celt` 、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="e1736-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1736-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e1736-110">Requirements</span></span>  
 <span data-ttu-id="e1736-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1736-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1736-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1736-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1736-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1736-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1736-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1736-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
