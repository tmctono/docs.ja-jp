---
title: ICorDebugChain::EnumerateFrames メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: 0b024d3396dfe1796fcb18afa122d4aee39c4ccc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132719"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="72e46-102">ICorDebugChain::EnumerateFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="72e46-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="72e46-103">チェーン内のすべてのマネージスタックフレームが格納された列挙子を取得します。これは、最新のフレームから始まります。</span><span class="sxs-lookup"><span data-stu-id="72e46-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72e46-104">構文</span><span class="sxs-lookup"><span data-stu-id="72e46-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72e46-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72e46-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="72e46-106">入出力スタックフレームの列挙子である、テキストフレームの列挙型オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="72e46-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72e46-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="72e46-107">Remarks</span></span>  
 <span data-ttu-id="72e46-108">チェーンは、スレッドの物理呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="72e46-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="72e46-109">`EnumerateFrames` メソッドは、マネージドチェーンに対してのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="72e46-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="72e46-110">デバッグ API には、アンマネージチェーンに含まれるフレームを取得するためのメソッドが用意されていません。</span><span class="sxs-lookup"><span data-stu-id="72e46-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="72e46-111">デバッガーは、この情報を取得するために他の手段を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72e46-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72e46-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="72e46-112">Requirements</span></span>  
 <span data-ttu-id="72e46-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72e46-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72e46-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72e46-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72e46-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72e46-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72e46-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72e46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
