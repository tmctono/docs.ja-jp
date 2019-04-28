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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7568f8ca3b92ef465ab595348f68895f389d61e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645319"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="7577b-102">ICorDebugChain::EnumerateFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="7577b-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="7577b-103">最新のフレームを開始する、チェーン内のすべてのマネージ スタック フレームを含む列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="7577b-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7577b-104">構文</span><span class="sxs-lookup"><span data-stu-id="7577b-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7577b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7577b-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="7577b-106">[out]スタック フレームの列挙子である ICorDebugFrameEnum オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7577b-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7577b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="7577b-107">Remarks</span></span>  
 <span data-ttu-id="7577b-108">チェーンは、スレッドの物理呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="7577b-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="7577b-109">`EnumerateFrames`メソッドは、管理対象のチェーンに対してのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7577b-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="7577b-110">デバッグ API では、非管理対象のチェーンに含まれているフレームを取得するメソッドが提供されません。</span><span class="sxs-lookup"><span data-stu-id="7577b-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="7577b-111">デバッガーは、この情報を取得するのにその他の手段を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7577b-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7577b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="7577b-112">Requirements</span></span>  
 <span data-ttu-id="7577b-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7577b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7577b-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7577b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7577b-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7577b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7577b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7577b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
